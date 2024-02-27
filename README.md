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
## PROGRAM



NAME: DEEPAK RAJ S

REG NO: 212222240023

```
import random
class VacuumEnvironment:
    def init(self, size):
        self.size = size
        self.agent_location = random.randint(0, size-1)
        self.dirt_locations = [random.randint(0, size-1) for _ in range(size)]
    def is_dirty(self, location):
        return location in self.dirt_locations
    def clean(self, location):
        if location in self.dirt_locations:
            self.dirt_locations.remove(location)
    def move_agent(self, action):
        if action == "left":
            self.agent_location = max(0, self.agent_location - 1)
        elif action == "right":
            self.agent_location = min(self.size - 1, self.agent_location + 1)
    def percept(self):
        return self.agent_location, self.is_dirty(self.agent_location)
class SimpleReflexAgent:
    def init(self):
        pass
    def action(self, location, dirty):
        if dirty:
            return "suck"
        elif location == 0:
            return "right"
        elif location == 1:
            return "left"
def main():
    size = 5
    environment = VacuumEnvironment(size)
    agent = SimpleReflexAgent()
    for _ in range(10):
        location, dirty = environment.percept()
        action = agent.action(location, dirty)
        if action == "suck":
            environment.clean(location)
        environment.move_agent(action)
        print("Location:", location, "| Dirty:", dirty, "| Action:", action)
if __name__ == "__main__":
    main()
```
