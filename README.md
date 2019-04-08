# world_simulator_exec
This is the executable file wrapped in a docker for world_simulator, background world for ECE 568 final project.
No source code included.

To run the world simulator without flakiness, type: "sudo docker-compose build" in the same directory with the yml file.
Then type "sudo docker-compose up". 

To run the world simulator with a different flakiness, go to "docker-compose.yml" file, change the command from bash -c "./wait-for-it.sh mydb:5432 --strict -- ./server 12345 23456 0" into bash -c "./wait-for-it.sh mydb:5432 --strict -- ./server 12345 23456 <flakiness_num>". Then do as last paragragh said.

Note flakiness ranges from 0 to 99. When flakiness equels 0, it mean the world will not deliverately drop any request it receives. As flakiness grows, the possibility that the world randomly drops requests will be larger. You can view this behavior as in real life "error in communication". That's also why we are having ack number for each requests. 