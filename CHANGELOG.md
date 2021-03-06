# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### TODO

- Implement front end UI interface via external application (React or Flutter TBD)
- Implement alert system via notifications (SMS, other to be determined)
- Improve scan system and clean up code
- Implement messaging queue architecture


## [1.0.1] - 2020-07-07

### Changed

- Standardized the class names of the Commands in UpperCamelCase
- Fix a missing CURL library in the Docker file

## [1.0.0] - 2020-07-05

### Changed

- Convert project into Lumen micro-service architecture
- Transform existing console interface to 'Activescan', solely responsible for analyzing weather alerts and other future data

### Added

- Docker file to initalize an Nginx+Alpine and mariadb infrastructure in a server or local Docker implementation

## [0.2.0] - 2020-06-04

### Added

- Add Counties table and implement relationship to each location for better data management
- Implement foreign keys

### Fixed

- Fixed data duplication issue resulting in a copy of every alert history being created each time the cron ran

### Changed

- Change the naming of LocationsInterface/LocationsRepository to be standardized with the County repository

## [0.1.8] - 2020-06-01

### Added

- Switch Eloquent queries to Repositories to improve code quality and elegance
- Implement Sentry

## [0.1.7] - 2020-05-19

### Fixed

- Properly clean up stale alerts

## [0.1.5] - 2020-05-05

### Added

- In order to optimize memory usage, a current conditions table has been added so only a few hundred results need to be read when looking for current conditions (instead of thousands, or tens of thousands)

### Changed

- Modify the Scan Alerts command to only parse the date into a Carbon object the first time, then use the object instead of parsing it repeatedly

## [0.1.4] - 2020-05-05

### Added

- Properly set distinct and latest record on the current alerts collection to ensure we don't end up with every historical alert

### Changed

- Remove extra rendering of the real time alerts VUE component

## [0.1.2] - 2020-05-05

### Added

- Add one-to-one relationships from the alert history to the alert type and locations
- Centralize initial landing page in new controller
- Add seeder with base "No alerts in effect" so we can simplify the initial logic

### Changed

- Add all current observed alerts to landing page
- Clean up demo VUE object
- Change "AlertDict" to "AlertType" for better clarity

## [0.1.0] - 2020-05-03
### Added
- Add Vue.JS to front end
- Install Laravel Echo Server
- Implement Socket.IO
- Add demo Vue component with dynamic updating to test proof of concept on live server

## [0.0.3a] - 2020-04-21
### Changed
- Fixed a missed semi-colon and failed test due to working at 0200

## [0.0.3] - 2020-04-21
### Added
- Improve code commenting
- Add catch-all to prevent exceptions and fatal errors during run-time when an unmatched alert description pattern is read

## [0.0.2] - 2020-04-21
### Added
- Release a more detailed README for the project
- Add Laravel scheduling to run the _**wscan:scanalerts**_ command every five minutes if a master cron job is enabled

## [0.0.1] - 2020-04-20
### Added
- Initial release with basic migrations, and simple commands to populate the tables with the links to the Environment Canada ATOM feeds as well as pull data from them.

### TODO
- Optimize the cost of pulling the alerts from the ATOM feed
- Create front end interactive interface and API feature for third party integration
- Write documentation for scheduling
