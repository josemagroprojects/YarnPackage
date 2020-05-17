Author: José Magro

Date: 01/05/2020 

# How to install packages in Framer X with Yarn 

Here's a short explanation of how to install a package in a Framer X project. We're going to use [Yarn](https://yarnpkg.com/), a package manager widely adopted by the community.


## What is a package manager?
The primary function of any package manager is to install a package — a piece of code that serves a particular purpose — from a global registry into an engineer's local environment. Each package may or may not depend on other packages. A typical project could have tens, hundreds, or even thousands of packages within its tree of dependencies.

These dependencies are versioned and installed based on semantic versioning (semver). Semver defines a versioning scheme that reflects the types of changes in each new version, whether a change breaks an API, adds a new feature, or fixes a bug. However, semver relies on package developers not making mistakes — breaking changes or new bugs may find their way into installed dependencies if the dependencies are not locked down.


## Part 1

**Install yarn**


At the website, you have a dedicated section that shows you how to [install it](https://classic.yarnpkg.com/en/docs/install#mac-stable)

Even though let's go step-by-step:

1. Open the terminal
2. enter this command `curl -o- -L https://yarnpkg.com/install.sh | bash` and press enter
3. when the installation is complete, insert the following command to see if Yarn is installed `yarn -v`
4. If it appears the version number, then you're ready to go


## Part 2
**Add a package**


In this part, we're going to install a package named [Moment](https://momentjs.com/), that manipulates and displays dates or hours.


Let's check each part of in detail:

1. Open framer
2. Go to the File menu and select the option ***Show Project Folder***
3. With  the project folder opened, go to the top of the folder window and drag the folder icon to the terminal, once the path appears press enter
4. In the terminal insert the following command `yarn add moment`, this tells yarn to install the package. You should pass the package name as an argument, in this case is moment
5. Once the installation is done, run the command `yarn list`, after check if the package you installed is listed in there


**Here's the video explaining**

https://www.loom.com/share/fb426e75c94e4655a2925ec739e450c7


## Part 3
**Use the package in framer**

In this part, let's use the moment package in framer. We're going to display the current day of the week. Let's go step-by-step:

1. Open a frame
2. Insert some text. It can "This text is going to be overridden"
3. At the Layout panel, go to the Override section, click the file dropdown and select Examples
4. Go to the Examples.tsx file. For that, click the brackets symbol in the left panel.
5. Once inside the file, eliminate everything unless this part: 

        import { Override } from "framer"

        export function TodaysDate(): Override {

            return {

            }

        }
6. Import everything inside the package using ```*``` and import it as an object named moment, like this:
        
        import * as moment from "moment"

7. For the last step, override the text using an object from the moment package:
   
        text: moment().format("dddd")

8. For the final code you should have something like this:
   
        import { Override } from "framer"
        
        import * as moment from "moment"

        export function TodaysDate(): Override {
            return {
                text: moment().format("dddd"),
            }
        }

9. Go to the section where you have the Frame, once there select the text, go to override and in the override option select TodaysDate
10. Press the Preview option at the top right corner, and if everything went well you'd see the current day you're at


**Here's the video explaining**

https://www.loom.com/share/645d47f871c3473491e2cd6c609614b1


Hope you enjoyed, thank you!