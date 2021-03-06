# UberSlack (Das Slackër)

* An Uber & Slack Integration API
* Built by App Academy students in the August 2015 cohort

## Overview

UberSlack enables Slack users to hail Über rides directly from their chat client with a command-line type interface. By utilizing slash commands ([https://api.slack.com/slash-commands][slashlink]) from the Slack API, Släcker allows the user to type in various commands (see Usage section below) to hail an UberX ride to a designated pickup location and designate certain options for the ride.

[slashlink]: https://api.slack.com/slash-commands

## Usage

All commands will follow the following format:
```
/uber [command] [extra parameters]
```

#### Hailing a Ride
To hail a ride, enter a 'ride' command in your Slack chat in the following format:
```
/uber ride [pickup address] to [destination address]
```

This can handle a variety of address formats:
```
/uber ride 1061 market st to 24 willie mays plaza
/uber ride 1061 Market St. to 24 Willie Mays Plaza
/uber ride 1061 market street san francisco to 24 willie mays plaza san francisco
```

And will return a JSON string notifying you of the status:
```
{"status":"processing","request_id":"6c265d45-3a1c-4434-ba73-0be5d2c2d14f","driver":null,"eta":12,"location":null,"vehicle":null,"surge_multiplier":1.0}`
```

#### Cancelling a Ride
You can cancel a ride by using the 'cancel' command:
```
/uber cancel
```

#### Uber Vehicles
To see the various Über vehicles that are available:
```
/uber products [destination address]
```

This will return a response like so:
```
The following products are available:
- uberX: The low-cost Uber (Capacity: 4)
- uberXL: Low-Cost Rides for Large Groups (Capacity: 6)'
```

#### Help
A help manual is available with the 'help' command:
```
/uber help
```
