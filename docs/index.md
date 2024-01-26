# Welcome to the Onboarding for Hydroponics!

[FAQs and Common Issues](https://www.notion.so/FAQs-and-Common-Issues-d0cd1165783843e1b3c2f8da77492a7a?pvs=21)

### What is Hydroponics?

Hydroponics is the technique of growing plants using water-based nutrient solutions instead of soil. Hydroponics could be the future of agriculture (dare we say aquaculture) because of hydroponic gardens’ compactness, fast growth, resistance to pests, and lower water consumption.

### Our Goals

As a PInT subteam one of our primary goals is to help you learn and grow as individuals by doing. If you’re not passionate about any of the existing subprojects that we’re working on, then talk to your lead and we can find a fit for you.

Automation’s goal is to create a living garden; that is, a garden that can give itself more water or nutrient substrate when it’s needed. We’re implementing this using a microcontroller that should check plant metrics (pH, water content, etc.) and deliver the nutrients a plan needs to survive. We plan to allow the community to interact with the hydro wall without needing to be there in person, so we have designed an API and are constantly improving our API and frontend dashboard so that we provide a good user experience.

### To Contribute

Visit our Computational Setup and Install Packages pages, which detail how you can install the software you need to succeed on Hydroponics.

[Computational Setup - General](computational_setup.md)

[Install Packages](packages.md)

Our GitHub is organized into several subdirectories, each with a focus on one aspect of the Hydro automation workflow. You can view our GitHub here: https://github.com/Olin-Hydro.

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
