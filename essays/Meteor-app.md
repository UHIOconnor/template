---
layout: essay
type: essay
title: Meteor, A Rocky Start
date: 2016-10-20
labels:
  - Meteor
  - App coding
---

Meteor to me has been a mixed bag. Trying to learn it over the past couple of weeks has been a trying expriance. compared to picking up
base html or semantic UI meteor has been a lot more involved. part of the diffuculty i suppose is based on meteor being a culmination of 
the other tools i ahve picked up. However it hasnt been all hard, for example the local application that meteor hosts makes it much simpler to debug code. This helps a lot because it helps of all the imports and tiny little issues that can break the app.

The most helpful thing i have found for learning about meteor is the code templates. For example in the template i was working with
used the following to sumbit entries into a table.
```
Template.Create_Student_Data_Page.events({
  'submit .student-data-form'(event, instance) {
    event.preventDefault();
    // Get name (text field)
    const name = event.target.name.value;
    // Get bio (text area).
    const bio = event.target.bio.value;
    // Get hobbies (checkboxes, zero to many)
    const hobbies = [];
    _.each(['surfing', 'running', 'biking', 'paddling'], function setHobby(hobby) {
      if (event.target[hobby].checked) {
        hobbies.push(event.target[hobby].value);
      }
    });
    // Get level (radio buttons, exactly one)
    const level = event.target.level.value;
    // Get GPA (single selection)
    const gpa = event.target.gpa.value;
    // Get Majors (multiple selection)
    const selectedMajors = _.filter(event.target.majors.selectedOptions, (option) => option.selected);
    const majors = _.map(selectedMajors, (option) => option.value);

    const newStudentData = { name, bio, hobbies, level, gpa, majors };
    // Clear out any old validation errors.
    instance.context.resetValidation();
    // Invoke clean so that newStudentData reflects what will be inserted.
    StudentDataSchema.clean(newStudentData);
    // Determine validity.
    instance.context.validate(newStudentData);
    if (instance.context.isValid()) {
      const id = StudentData.insert(newStudentData);
      instance.messageFlags.set(displaySuccessMessage, id);
      instance.messageFlags.set(displayErrorMessages, false);
    } else {
      instance.messageFlags.set(displaySuccessMessage, false);
      instance.messageFlags.set(displayErrorMessages, true);
    }
  },
});
```
Trying to create the following code from scratch would be difficult and would take much longer to learn than being abe to see the
whole picture. This is Expecially true since this allows us to implement the code and meteor allows us easily see how the app 
implemnts the code.

Overall i have both enojoyed working with meteor when im understanding the code and dreaded it while im not. Meteor certanily intrests me as a app building platform. It certainly seems fairly diverse in what you can accomplish when you know the ins and outs of Meteor. 
Once i get the hang of Meteor I hope to program apps significantly easier.
