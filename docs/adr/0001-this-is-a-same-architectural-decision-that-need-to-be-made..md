# This is a same architectural decision that need to be made.

* Status: proposed
* Date: 2021-08-06

Technical Story: The fub-bar project has encounted a snafu, due to poor planning.

## Context and Problem Statement

Due to poor planning, when a user navigates to page ABC, and clicks on the "Brave New World" button, the application attempts to load the ABC micro-app from our internal file-repository.  If for some reason the file-repository is offline, the micro-app cannot be loaded resulting a failure, to the user.

## Considered Options

* Build HA instances of file-repository
* Do Nothing (Keep current architecture)
* Build out a secondary extenal CDN

## Decision Outcome

Chosen option: "Build out a secondary extenal CDN", because comes out best. when considering cost / risk analysis.

### Positive Consequences

* Build greater confidence in our brand, with limit cost.
* I like it..

### Negative Consequences

* All micro-apps, will need to be scanned to ensure that no privilege data/info will be deployed externally.

## Pros and Cons of the Options

### Build HA instances of file-repository

Standard HA Strategy

* Good, because We own it and have complete control
* Bad, because Could potential increase operational cost up to 3 times current expenses.

### Do Nothing (Keep current architecture)

Don't do anything, this might not happen again or will have minimal impact.

* Good, because Keeps cost low..
* Bad, because If happens again during prime time, we are screwed

### Build out a secondary extenal CDN

Leveraging Amazon's CDN platform, we could push all micro-apps to a CDN externally hosted.

* Good, because Provided additional location the application can utilze as a failback, in the event our local CND is not available.
* Good, because Amazon charges by utilization, so it would me more cost effective..
* Bad, because Got to deal with security and vunerbility issues having the content externally available.
