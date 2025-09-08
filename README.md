<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: PREETHI A K</h3>
<h3>Register Number: 212223230156</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>

### PROGRAM

```

rooms = ["Room1", "Room2"]
patients = {r: float(input(f"Enter temperature in {r}: ")) for r in rooms}
cycles = int(input("Enter number of cycles: "))

p, room = 0, rooms[0]
for i in range(cycles):
    print(f"\nCycle {i+1}:")
    temp = patients[room]
    if temp > 98.5:
        print(f"{room}: fever ({temp}°F). Prescribing medicine.")
        p += 1
        patients[room] = 98.0
    else:
        print(f"{room}: healthy ({temp}°F).")
    room = rooms[1] if room == rooms[0] else rooms[0]
    print(f"Moving to {room}.")
    p -= 1
print(f"\nFinal Performance: {p}")


```

## OUTPUT

<img width="549" height="370" alt="image" src="https://github.com/user-attachments/assets/86f938e4-0acb-4f6b-b1d3-97b3f3fa03d1" />

## RESULT

Thus the Developing AI Agent with PEAS Description was implemented using python programming.




