**Personal Information**
=====================
- Name: Oskars Vismanis
- Email: oskarsvismanis@gmail.com
- Github: [sniegs](https://github.com/oskarsVismanis)
- Location: Riga, Latvia
- Time Zone: UTC+2
- University: Riga Technical university
- Major: Intelligent Robotic Systems

**Project Description**
=====================
- Name: [Better Parallel Planning with MoveIt 2](https://moveit.ros.org/events/2023-google-summer-of-code/#better-parallel-planning-with-moveit-2)
- Mentors: Sebastian Jahr, Jafar Uruç
- Goals:
  **Plan for accomplishing them in detail explained below**
  - **Enable parallel planning in the move_group interface**
  - **Make parallel planning usable in RVIZ Motion Planning Panel**
  - **Visualize different parallel planning solutions in RVIZ**
- Deliverables:
  - **The ability to choose and use the parallel planning pipeline from the move_group_interface**
  - **Interactable parallel planning option in the RViz Motion Planning Panel**
  - **Option to visualize the different solutions found while planning paralelly from the Displays panel**
  - **All code correctly formated, tested, reviewed and merged**


**About me**
=====================
I am currently studying in Riga Technical university, in a Masters programe "Intelligent Robotic Systems", in the second semester. I currently work half-time as a research assistant in the Institute of Electronics and Computerscience in Riga, where I have been constantly studying robots and working with them for the past 4 years, mostly using ROS and MoveIt, with both C++ and Python. Working on different tasks, I have made multiple applications using the UR5 and UR5e robots, most notable of them being a pick-n-place application for two different objects with two robots working in the same workspace, where I was responsible for making the whole two robot setup work. That included:
 - making the whole .udrf/.xacro setup for both of the robots to be in the same workspace,
 - figuring out a calibration system for two robots (which is based on a hand-eye calibration programe for one robot, which I made using Python, PyQt5 for GUI etc.)
 - managing each robots tasks, which was done with state machines, using SMACC
 - creating and managing different actions for each robots, such as moving to defined and undefined positions, actuating both parallel and vacuum grippers and so on.

From this task I also made my proffessional Bachelor's thesis "Research and development of multi industrial robot collaborative systems" for which I got a 10.

Link to a repo of a part of the application that I made [edi_sm_ur5](https://github.com/oskarsVismanis/edi_sm_ur5)

Besides my experience, I am very interested in robotics and programming and I really want to learn contributing to open-source projects. I like to take up tasks that make me grow both professionally and as a person.

**Homework**
=====================
- Study ROS 2 and MoveIt 2, read MoveIt 2 concepts
- Get familiar with open-source contributions by contributing to issues
- Study the "move_group_interface" planning pipeline and the "parallel planning API for
  moveit_cpp"

**Plan**
=====================

- Steps
  1. **Enable parallel planning in the move_group interface**:

        Mainly the first thing to do would be to thoroughly understand how the existing planning process works, by exporing the function and service connections. 
        
        My initial idea for accomplishing this task is by, first, adding the option to set the `setPlanningPipelineId` input to *parallel_planning*. This would also require the planner_id to allow multiple planner id's. Maybe with this setting the planner_id is required to be multiple strings. With this choice, the `MotionPlanResponse PlanningComponent::plan(...)` would be run, then, similar to the example, the shortest path would be chosen, or this could be left as an option for the user, to choose the first one found, the shortest, smoothest etc.
        
        Additional option is to make the parallel planning pipeline the default option, but have it by default be set to only one planner, and, when needed, you could just add other planners.

  2. **Make parallel planning usable in RVIZ Motion Planning Panel**:

        First and foremost, I would like familiarize myself with how the Motion Planning Panel is set up, mainly the motion_planning_rviz_plugin. See how everything is connected to the planning pipeline. 
        
        For this, the motion_planning_rviz_plugin would need to be updated. What I imagine is, instead of planning library being under the context page, it could be a seperate "Planning" page, where the option for single or parallel planning could be ticked by a check_box. With the parallel planning checked, the option to choose multiple planners and multiple pipelines would show up.
        
  3. **Visualize different parallel planning solutions in RVIZ**:

        Since the chosen plan is already being visualized, this should probably be a checkbox under the MotionPlanning part of the Displays panel. In this case the motion should only be planned, before being executed. The checkbox would probably go under the `Planned Path` part of the MotionPlanning Display Type. Maybe you could check each of the available plans and they would be made semi-transparent, and the color for each of them would be different by default and also open to change from the user. Then, when planning, each of the solutions could be shown depending on which checkboxes are ticked.
        
        This would also require me to first study the motion_planning_rviz_plugin code, to see how the Displays and MotionPlanning panels are set up, to add these options.  

- At first my idea is to prioritize these tasks and only move to the second and third tasks when the first one is finished. I feel like they kind of depend on each other and the second and third one can also be combined into one.

**Timeline**
=====================

## Official overview

- **May 4**: accepted GSoC contributor projects announced;
- **May 4 - May 28**: community Bonding Period | GSoC contributors get to know mentors, read documentation, get up to speed to begin working on their projects;
- **May 29**: coding officially begins;
- **July 10 - July 14**: Midterm evaluation;
- **July 14 - August 21**: work Period | GSoC contributors work on their project with guidance from Mentors;
- **August 21 - August 28**: final week.

## Details

- **before May 4**
  - communicate with mentors to understand the details and goals of the project;
  - do the homework

- **May 4 - May 28**
  - active research about the project

- **July 10 - July 14**
  - prepare for phase 1 evaluation

- **July 14 - August 21**
  - coding

- **August 21 - August 28**
  - code style and quality review, dev documentation
  - prepare for final evaluation

**Why me**
=====================
I have been working with ROS and MoveIt for some time now and I am already working with ROS 2 and MoveIt 2 starting this year onwards. I am very interested in robotics, that's why I chose the only not-so-industrial robotics course in Latvia that I could find. Using ROS 2 and MoveIt 2 is directly connected to the tasks I do at my workplace and will definitely be connected to my Masters thesis, which will be due summer 2024. All of these are high priority reasons for why I will be very motivated to work on this project. Also I have experience working with ROS, MoveIt, C++, move_group_interface, move_group etc., but I lack the experience with contributing to open-source projects, which includes lack of knowledge about cody styling and documentation, which all are directions I want to improve on greatly. Overall I am knowledge hungry and I feel like, if I can contribute back while also learning a lot myself, it's the perfect opportunity!
