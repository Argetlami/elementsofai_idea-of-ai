<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

# AIssistant

Final project for the Building AI course

## Summary

AIssistant (aissistant) is an home automation AI acting as a centralized automatic controller for home IoT devices and peripherals. AIssistant learns an user routine and adjusts its workflow accordingly to build an automated environment for the user. 

## Background

IoT devices and smart systems play a big part in a modern home. These devices consist of remote controlled coffee machines, automatic locks, smart lights and extensive audio systems, to name a few. Those devices however lack a centralized automated workflow and need an user input to operate.

Some devices are hard to configure and have confusing user interfaces to work with. The aim of this project is to create a centralized user routine based controller to control these devices with. One should not need to use multiple different apps to operate their devices with, especially as these systems often come with an open API for it to be controlled with.

The project is not only to create a scalable unified user interface for all the devices, but also create a learning AI to automate the actions with. Waking up every weekday morning at the same time to make a coffee? It can be automated. Remotely switching a smart relay to turn up your computer when the coffee is ready? Automated as well. Forgot to put an alarm altogether? Don't worry, the AI set it up for you based on your typical schedule.

## How is it used?

Setting up an AIssistant is simple. The system will work with existing data and learn new things by your actions without a need of user input.

At first, an empty home is seen. The configuration starts by adding smart devices. This can be done automatically with a scan of local area network or by inputting items one by one. The added items are checked against the API database to see if these devices are already supported by the system.

When devices have been added, a basic routine is set up. This starts with a typical weekday.

| App does | User does |
|---|---|
| Make coffee | Drink coffee |
| Start computer | Go to a computer |
| Open news site | Read news |
| Lock doors | Leave to work |
| Open doors | Arrive from work |
| Remind for exercise (start upbeat song etc.) | Exercise (or try to procrastinate) |
| Order food or pop up a recipe on fridge monitor | Order or make a dinner |
| Start a next episode from a serie | Watch a serie |
| Remind to go to bed, dim lights | Go to bed |

The figure above can represent a typical workday in a middle of a week. Normally all the things app and the user does are manual and/or controlled by another separate app or two. All this can be automatic and done without an user input, or minimal user input such as activity suggesting notifications.

As weekends and holidays are more flexible and spontaneous, a typical weekend is learned from scratch. Typically waking up at 09:00 when going to bed at 01:00? The system will learn your sleep routine and can adjust itself by your previous sleep pattern and possible sleep deprivation, for example. Soft waking on weekends by slowly brightening lights and/or with a low-volume peaceful song.

The system can adjust to calendar events, notifications, messages, basically anything it is allowed to peek into. Arising a question about privacy and data protection, it can be said that all the gathered data is merely processed and not sent or saved anywhere as it is. For example, a message confirmation for a meeting at 12:00 at home simply sets an event for the system to know that someone is expected to come at some point around 12:00, and the details are not saved nor sent "for telemetry and quality assurance purposes". System might even pop up a predictive notification asking if you'd like to get some coffee ready when the doorbell rings.

## Data sources and AI methods

The original source of user data is the user input. The system does learn, eventually, but to ensure a good starting point a simple predefined routine can be used.

Along with user input, the user data is gathered with learning. These seemingly repetitive actions can though be unlearned or ignored, if the user wants so. Some functions, such as unlocking doors, can be questioned first by presenting a notification, for example, if the user wants to unlock the doors and whether to do this automatically.

The devices to be used are grathered via local area network and/or user input. The API's for these devices are kept on a public server and a copy of these entries are made to the system. A list of devices not found on a database are kept and checked regularly if a support for these devices is available. This data is gathered by hand from public information about these API's, for example utilizing https://the-api-collective.com/category/iot as the base.

## Challenges

There are some questionable results coming from this sort of automation. What to do if the users phone has ran out of battery and the doors are automatically locked? What if someone steals your smart watch, can it be used to gain an access to your house? What if user is trying to change their lifestyle, for example is trying to quit smoking but the automatic repeating click of door unlocking is an unwanted reminder for a smoke break?

Another challenge is that many IoT devices use proprietary communication and have no public API. These devices cannot be easily integrated to the system and renders the whole thing troublesome and hard to set up. The proper automation might require an user to purchase additional compatible hardware to be used with the system.

## What next?

The hypotethical system can be improved with additional cooperation with IoT device providers. If more providers are supported by the system, it grow to be a standard.

Programming-wise the backend system could be done with Rust or similar high-efficiency language. The backend could be ran on a Raspberry Pi, for example, to ensure consistent uptime and persistent database. There needs to be an app to be used on handheld devices, such as mobilephones and smart watches for example, and on a PC, as a self-hosted solution for example.

## Acknowledgments

This project was an inspiration coming from existing assistant programs such as [Amazon Alexa](https://developer.amazon.com/en-US/alexa) and [Google Assistant](https://assistant.google.com). Neither of these are open source nor have a focus on privacy. This project aims to be a solution for people who would like to have such functionality but in a private environment without sharing their habits or profile. There are no such projects I am aware of, yet I am sure there are similar existing solutions out there.
