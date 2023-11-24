# rc-http

The RC HTTP car is a RC vehicle that can be controlled via a websockets connection from either the host computer or a hub unit. The basic concept is the Mario Kart Live thing that nintendo made a few years ago, but controlled via the internet. Further down the road it will integrate with Twitch API, allowing for dynamic user management, like a time limit on users use time in a rc vehicle, or allowing chat bans for losers of rc games.

The front end will be a React JS website that a user can control an RC vehicle with WASD / spacebar control. It will display the camera feed connected to the rc unit, with a HUB displaying game / user stats overlayed on top. When a user wants to join, the hub owner sends a command to the hub. The hub unit will send a command to AWS, which will return a URL from an API Gateway instance connected to a Lambda function.. The returned URL will display the front end for that instance's RC car. 

The back end will be a Raspberry Pi as the hub unit. It will handle starting new instances / stopping closed connections for rc units, user management and twitch integration, and handle the network integration from the host's network. The Pi unit will host websocket connections from the frontend websites and handle the commands to their respective rc units. 
