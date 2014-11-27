# Pipeline Templates

Templating helps to create reusable workflows in order to make tasks like creating and maintaining branches, and managing large number of pipelines easier.

## Creating Pipeline Templates

Pipeline Templates can be managed from the Templates tab on the Administration Page.

![](../resources/images/pipeline_templates.png)

Clicking on the "Add New Template" brings up the following form which allows you to create a fresh template, or extract it from an existing pipeline. Once saved, the pipeline indicated will also start using this newly created template.

![](../resources/images/add_new_template.png)

A template can also be extracted from a pipeline using the "Extract Template" link. This can be found on the "Pipelines" tab in the Administration page.

![](../resources/images/extract_template_from_pipeline.png)

### Example

As an example, assume that there is a pipeline group called "my-app" and it contains a pipeline called "app-trunk" which builds the application from trunk. Now, if we need to create another pipeline called "app-1.0-branch" which builds 1.0 version of the application, we can use Pipeline Templates as follows

## Using Administration UI

-   Create a template "my-app-build" by extracting it from the pipeline "app-trunk", as shown in the previous section.
-   Create a new pipeline "app-1.0-branch" which defines SCM material with the branch url and uses the template "my-app-build".

## Using XML

### Editing Pipeline Templates

Go Administrators can now enable any Go user to edit a template by [making them a template administrator](dev_authorization.md#template-admin).

Template administrators can view and edit the templates to which they have permissions, on the template tab of the admin page. Template Administrators, will however not be able to add, delete or change permissions for a template. They will also be able to see the number of pipelines in which the template is being used, but not the details of those pipelines.

![](../resources/images/template_admin_edit_template.png)

### Viewing Pipeline Templates

Pipeline Templates can now be viewed by Administrators and Pipeline Group Administrators while editing or creating a Pipeline.

![](../resources/images/template_view_on_pipeline_tab.png)

Clicking on the icon indicated by arrow will display the following:

![](../resources/images/view_template_popup.png)

The pop-up shows the extract of the template "Services-Template" configured for the pipeline "Service\_1".

1.  Shows the details of the job "compile-job" configured for the stage "compile".
2.  Indicates that the working directory set for the task is "go/service\_1", which is followed by the "\$" symbol and then the command.
3.  If any "On Cancel Task" has been configured, it will be indicated like this.
4.  Shows the "Run If Condition" for this task.

#### See also...

-   [Templates - Configuration Reference](configuration_reference.md#templates)