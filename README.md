<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Saravanan N</h3>
<h3>Register Number/Staff Id: TSML006</h3>


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
class MedicinePrescribingAgent:
    def __init__(self, rooms, patients):
        self.performance = 0
        self.rooms = rooms
        self.patients = patients
        self.current_room = rooms[0]  # Start at first room

    def sense(self):
        """Sense patient temperature in current room"""
        temp = self.patients[self.current_room]
        return temp

    def treat(self, temp):
        """Treat patient if unhealthy"""
        if temp > 98.5:
            print(f"Patient in {self.current_room} has fever ({temp:.1f}°F). Prescribing medicine...")
            self.performance += 1
            # After treatment, reset temperature to healthy
            self.patients[self.current_room] = 98.0
        else:
            print(f"Patient in {self.current_room} is healthy ({temp:.1f}°F). No medicine needed.")

    def move(self):
        """Move to another room (performance decreases)"""
        next_room = self.rooms[1] if self.current_room == self.rooms[0] else self.rooms[0]
        print(f"Moving from {self.current_room} to {next_room}...")
        self.current_room = next_room
        self.performance -= 1

    def run(self, cycles):
        """Run the agent for a number of cycles"""
        for _ in range(cycles):
            temp = self.sense()
            self.treat(temp)
            self.move()
        print(f"\nFinal Performance Score: {self.performance}")


# ----------------- MAIN PROGRAM -----------------

# Input from user
rooms = ["Room1", "Room2"]
patients = {}

for room in rooms:
    temp = float(input(f"Enter patient temperature in {room} (°F): "))
    patients[room] = temp

cycles = int(input("Enter number of cycles the agent should run: "))

# Run the agent
agent = MedicinePrescribingAgent(rooms, patients)
agent.run(cycles)



```

## OUTPUT

<img width="667" height="255" alt="image" src="https://github.com/user-attachments/assets/462a68f6-9c90-4c05-aa3c-001bd6e51b4c" />




