# **User Management Screen Specification Overview**

This document outlines the user interface specifications for the User Management Screen. 
The screen allows administrators to view, add, and manage users within the system. 
The interface is divided into two main sections: the user list and the new user form.


![image](https://github.com/daffytryin/User_Management_Screen_Specification/assets/136614755/23253889-e523-45d9-afa9-9a9912f52524)


## UI Components

### User List

#### ID Column

Displays the unique identifier for each user. Defined as integer. It has static, non-editable behaviour.

#### User Name Column
Displays the username of each user. Defined as string. It has static, non-editable behaviour.

#### Email Column

Displays the email address of each user. Defined as string. It has static, non-editable behaviour.

#### Enabled Column

Indicates whether the user account is enabled. Defined as boolean. Static, non-editable.

#### Hide Disabled User Checkbox

When checked, hides all disabled user accounts from the list. It is a checkbox. Filters the user list to show only enabled users.

### New User Form

#### Username Field

Input textbox field for the new user's username. Editable. Required. Cannot be NULL.

#### Display Name Field

Input textbox field for the new user's display name. Editable. Optional. Can be NULL.

#### Phone Field

Input textbox field for the new user's phone number. Editable, optional. Can be NULL.

#### Email Field

Input textbox field for the new user's email address. Editable, required. Cannot be NULL.

#### User Roles Dropdown

Dropdown menu to select the role(s) of the new user. Editable, required. Options include Guest, Admin, and SuperAdmin. Cannot be NULL.

#### Enabled Checkbox

Checkbox to indicate if the new user account should be enabled. Editable, default is unchecked. Cannot be NULL.

#### Save User Button

Button to save the new user information. When clicked, validates the form and saves the new user if validation passes.


## Initial State

* The user list displays all users with their ID, username, email, and enabled status.
* The "Hide Disabled User" checkbox is unchecked by default.
* The new user form fields are all empty.
* The "User Roles" dropdown is set to its default value.
* The "Enabled" checkbox is unchecked.
* The "Save User" button is enabled.


## Behaviors of OnClick

### Hide Disabled User Checkbox

When checked, the user list updates to hide users with the "Enabled" status set to false. When unchecked, all users are displayed.


### Save User Button

Validates that the "Username," "Email," and "User Roles" fields are filled out. If validation passes, adds the new user to the user 
list and clears the form. If validation fails, displays an error message indicating the required fields.

## Error Handling

### Form Validation Errors

Display a message next to the respective field if it is left empty and is required. Prevent the form from being submitted if any required fields are missing.
