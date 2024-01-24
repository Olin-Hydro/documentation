# Welcome to the Onboarding for Hydroponics!

[FAQs and Common Issues](https://www.notion.so/FAQs-and-Common-Issues-d0cd1165783843e1b3c2f8da77492a7a?pvs=21)

### What is Hydroponics?

Hydroponics is the technique of growing plants using water-based nutrient solutions instead of soil. Hydroponics could be the future of agriculture (dare we say aquaculture) because of hydroponic gardens’ compactness, fast growth, resistance to pests, and lower water consumption.

### Our Goals

As a PInT subteam one of our primary goals is to help you learn and grow as individuals by doing. If you’re not passionate about any of the existing subprojects that we’re working on, then talk to your lead and we can find a fit for you.

Automation’s goal is to create a living garden; that is, a garden that can give itself more water or nutrient substrate when it’s needed. We’re implementing this using a microcontroller that should check plant metrics (pH, water content, etc.) and deliver the nutrients a plan needs to survive. We plan to allow the community to interact with the hydro wall without needing to be there in person, so we have designed an API and are constantly improving our API and frontend dashboard so that we provide a good user experience.

### To Contribute:

Visit our Computational Setup and Install Packages pages, which detail how you can install the software you need to succeed on Hydroponics.

[Computational Setup - General](https://www.notion.so/Computational-Setup-General-751cbe826a9f4a2fa62c351c19af5d31?pvs=21)

[Install Packages](https://www.notion.so/Install-Packages-e498eccb0dc74e59ba2a6f249f6f7667?pvs=21)

Our GitHub is organized into several subdirectories, each with a focus on one aspect of the Hydro automation workflow. You can view our GitHub here: https://github.com/Olin-Hydro.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/8469ebe1-5030-4ff4-9e93-da19dccf0706/dbbf3a3d-b1ef-4f4c-9f4c-4167e1eecc98/Untitled.png)

### Hydrangea

Hydrangea is a messenger between all the component. It’s an Application Programming Interface (API) written in Python, which is essentially a contract between anything application that has a distinct function. Here’s how [Amazon Web Services](https://aws.amazon.com/what-is/api/#:~:text=on%20your%20phone.-,What%20does%20API%20stand%20for%3F,of%20service%20between%20two%20applications.) describes it: API “defines how the two communicate with each other using requests and responses.”

We are constructing a path where the microcontrollers, database, and the frontend dashboard can all interact with each other and communicate. Currently, we are using a REST API architecture with routes built for `GET`ting, `POST`ing, and updating (`PUT`ting):

- Configuration settings (`Config`) for scheduling sensor readings (`SensorSchedule`) and actuators (`SASchedule`, `RASchedule`)
- Gardens (`Garden`), pods (`Pod`), sensors (`Sensor`), reactive actuators (`Reactive_Actuator`), and scheduled actuators (`Scheduled_Actuator`)
- Commands (`Command`) for a specific execution of an actuator
- Various logs for sensors (`Reading`), scheduled actions (`Scheduled_Action`), and reactive actions (`Reactive_Action`)

This API uses [FastAPI framework](https://fastapi.tiangolo.com/) and AWS Lambda function to host. We are using MongoDB as our database and `pymongo` library for Python interface.

You’ll need Python 3.10+ and [MongoDB Community Edition](https://www.mongodb.com/docs/manual/administration/install-community/#std-label-install-mdb-community-edition) to start contributing.

### Saffron

Saffron is the frontend page that graphically displays data and provides convenient controls for the hydroponic system. It’s a dashboard for viewing the gardens and pods registered in the database and their corresponding data collected from the microcontroller — such as sensor readings, actuator logs, and etc. The repository uses mainly Typescript and React (”a free and open-source front-end JavaScript library for building user interfaces based on components,” [Wikipedia page on React](<https://en.wikipedia.org/wiki/React_(software)>)). Additionally, we use `axios` library for concise API requests and error handling. The graphic designs and mockups (made by Jasper K. `23) are available on [this Figma page](https://www.figma.com/file/g259C0UL7i5YMckjOJcDcR/Hydro-Frontend-V0.2?type=design&node-id=0-1&mode=design).

You’ll need Node.js and `npm` to start contributing.

### Mother-nature

Mother Nature is a high level controller written in Golang and applied using AWS Lambda. It acts as a checker for plant condition and communicates with the Hydro API to ensure plant health. We’re trying to move away from Mother Nature as it is over-engineered for our purposes.

### Mini-Gardener

Mini-Gardener is an embedded application for ESP-8266 that controls sensors and actuators, and communicates relevant data to database and/or frontend dashboard via Hydrangea (API). It’s written in C++ and uses PlatfromIO for VSCode IDE integration. The purpose of Gardener is to provide control over physical electronic components and automate the process of nurturing plants by running on provided logic and schedules.

You’ll need PlatformIO to start contributing.

**Let a lead know what you would like to work on and we’ll invite you to collaborate!**

Questions from Documentation Review:

- Where is the DB hosted?
- Why is it hosted on MongoDB and not AWS when the API is hosted on AWS
- What does the architecture look like geographically?
- Mentorship?
- Include diagram in docs
- What is least clear about our platform?
  - “I feel like i have a better picture looking at this diagram, but there’s a lot happening”
  - If i had to guess I would guess like the pH changed or something so that gardener sends commands to API and you send back configs to the local system
  - Don’t know what’s happening with mother nature
- Can you guess what components are hosted on what services?
  - Web-UI
    - React
  - Sensor Data
    - mongoDB
  - Data API
    - hosted on AWS lambda
    - using Python
  - In short, yes!
- List specific projects for students to work on?
  - if the student doesn’t want to work on one of the existing projects, then they can come to you
  - otherwise, list projects that they can work on
- FAQs and Common bugs page
  - Node.js error that keeps happening with version mismatch
- How does our workflow look like? Need to write workflow—PRs? Fork then push?
  - Do an exercise and do code review that exercise to get used to workflow?
  - They should be trying things themselves and in general not getting stuck (if they get stuck they can come to you but shouldn’t realllllly need to)
- Have students try out our docs and figure out what we still need / would benefit from
