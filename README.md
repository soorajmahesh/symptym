# Symptym

Symptym is a telemedicine app built around an AI voice agent. The idea is pretty simple: instead of filling out long forms or bouncing between different health apps, you just talk to the app about how you're feeling. It knows your medical profile, asks follow-up questions, and can connect you to a video call when you need one.

Note: Symptym is meant to help with triage. It is not a replacement for an actual doctor's diagnosis.

## Project Goal

Getting basic medical help is more of a hassle than it should be. The goal of Symptym is to make that first step easier by letting patients describe their symptoms out loud, get a personalized preliminary assessment based on their history, and hop on a video call, all from one app with a secure backend holding their info.

## MVP Scope

These are the "Do" items from my Eisenhower Matrix, the things the app needs to work at all:

1. **Voice agent** - the user talks to an AI agent about their symptoms. It uses their medical profile to give a more personalized response and a short triage summary.
2. **Video call interface** - in-app video calling, built on top of an existing video streaming service.
3. **Auth / AWS backend** - sign up and login, plus secure storage for the medical profile and past conversations, hosted on AWS.

Some parts I'm intentionally not building from scratch ("Delegate"):

- Disease data from Cambridge's list of diseases
- Drug data from a list of all drugs sold in the U.S.
- An existing video streaming service/SDK instead of writing my own

## Future Plans

From the "Schedule" quadrant, planned for V2.0 once the MVP is done:

- **Doctor side of the app** - a dashboard where providers can see patients and review the AI triage reports
- **Medicine order interface** - ordering and refilling prescriptions
- **Insurance billing / insurance linking** - letting patients link their insurance and handle billing in the app

I also cut one idea completely: a doctor-facing interface for filing insurance claims. It's not core to what the app is trying to do.

## Tech Stack

- **Frontend:** React Native (iOS and Android from one codebase)
- **Backend:** Python + FastAPI, deployed on AWS
- **Auth:** AWS Cognito
- **Database:** PostgreSQL
- **AI:** LLM API with speech-to-text and text-to-speech for the voice agent
- **Video:** third-party video streaming SDK

## Repo Structure

```
symptym/
  docs/          Eisenhower Matrix, system diagram, design notes
  src/
    mobile/      React Native app
    backend/     FastAPI server
  tests/         unit and integration tests
  README.md
```

## Planning Docs

- [Eisenhower Matrix](docs/eisenhower-matrix.png)
- [System Diagram](docs/system-diagram.png)

## Build Plan

I'm building this in chunks and committing as I go:

1. Repo setup, README, planning docs
2. AWS backend skeleton and auth
3. Storing the user's medical profile
4. Voice agent (speech to LLM and back, with profile context)
5. Video call interface
6. Hooking the mobile app up to the backend end to end
7. Testing, cleanup, and demo

## Status

Work in progress. This is my final project for CS 19300.
