= Ubimix projects =

This project contains Maven configuration files used to checkout all projects
from remote repositories, build and install them. This configuration 
is used also to prepare Eclipse development environment.

== How to checkout all projects? ==

> cd checkout
> mvn initialize

These operations will checkout all projects from remote repositories and store 
them in a local folder. This operation creates a temporary POM file containing 
references to all loaded modules.
By default this configuration loads all projects in the "../org.ubimix.projects" 
folder. This value could be replaced using the "workspaceDir" variable:

> cd checkout
> mvn initialize -DworkspaceDir=<PATH_TO_PROJECT_DIR>

List of all projects is loaded from the "checkout/projects.json" file.
To re-define the list of projects to load you can use the "projectListFile"
variable:

> cd checkout
> mvn initialize -DprojectListFile=<PATH>/projects.json

An example of project list re-definition and the resulting workspace directory:

> cd checkout
> mvn initialize -DworkspaceDir=../../myworkspace -DprojectListFile=../../myProjects.json
 

== How to compile and install all projects? ==

1) Go to the workspace directory where all projects were checked out.
2) Launch the maven build configuration:

Clean/install: 
 
> cd ../org.ubimix.projects
> mvn clean install

== How to create/update Eclipse configuration? ==

1) Go to the workspace directory where all projects were checked out.
2) Launch the maven build configuration:

> cd ../org.ubimix.projects
> mvn eclipse:clean eclipse:eclipse

== How to import projects into Eclipse ? ==

To import projects in the Eclipse workspace you need to perform the following
actions:
* "File" > "Import..."
* Select "General" > "Existing Projects into Workspace"
* Click the "Next >" button
* In the field "Select root directory:" put the full path to the "./projects"
  sub-folder. You can use a dialog box activated by the "Browse..." button and 
  click "Validate". 
* Select all projects and click the "Finish" button. 
  Note: You should uncheck the "Copy projects into workspace" option to avoid 
  duplication of projects on your disk. 

== How to re-define the project checkout and build directory? ==

All projects are checked out and compiled in the folder defined by 
the "workspaceDir" variable. This variable contains a path relative to the
"checkout" or "build" directory. So the "../projects" value points to the
"projects" sub-folder in this project.  

To re-define the project folder:
> mvn initialize -P checkout -DworkspaceDir=../ubimix-projects
> mvn clean install -DworkspaceDir=../ubimix-projects

In this case all projects are checked out and compiled in the "ubimix-projects"
sub-folder.
