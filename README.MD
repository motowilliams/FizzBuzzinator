# FizzBuzzinator #


## Build ##
To restore packages, compile and run the unit tests run the following in the repository root in a powershell prompt

    .\build\run.ps1

you can run specific tasks if needed by

    .\build\run.ps1 -task your_task_name

## Build Info ##
This project uses Psake to build the artifacts.

**run.ps1** is just a bootstrap script for convenience

The build steps include:

1.  Determining what path your git install is located
2.  Nuget download
3.  Nuget update if you already have the executable
4.  Nuget package restore 
5.  Compile
6.  Run xunit tests
7.  Copy output to $/artifacts
8.  Drop a version file (based off of git describe)
9.  Drop a Release Notes file based off the commits from last tag

Things that would need to be done for a real project

- Run integration and other test suites based
- Update assembly versions
- Get test output to a location for the CI process to pick up
- Get hooked with Octpuss Deploy or other CD process to get things deployed

## FizzBuzzinator.exe ##

In the .\artifacts\AcmeCompany.FizzBuzzinator.Console directory you will find AcmeCompany.FizzBuzzinator.Console.exe

This application will run the default 1-100 routine with no arguments passed

    .\artifacts\AcmeCompany.FizzBuzzinator.Console\AcmeCompany.FizzBuzzinator.Console.exe

or you can pass an arbitrary limit to your FizzBuzz needs

    .\artifacts\AcmeCompany.FizzBuzzinator.Console\AcmeCompany.FizzBuzzinator.Console.exe 42

you can also pass a 'magic' string of max which will run the entire range from 1 to 2,147,483,647 with the following

    .\artifacts\AcmeCompany.FizzBuzzinator.Console\AcmeCompany.FizzBuzzinator.Console.exe max
