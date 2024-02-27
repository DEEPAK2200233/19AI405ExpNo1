<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Saravanan N</h3>
<h3>Register Number/Staff Id: TSML006</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>VACUUM CLEANER:</h3>
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
    <td><strong>VACUUM CLEANER</strong></td>
    <td><strong>ABSORB DIRT</strong></td>
     <td><strong>Rooms</strong></td>
    <td><strong>CLEANING AGENT</strong></td>
    <td><strong>Location</strong></td>
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

<h3>PROGRAM</h3>
NAME: DEEPAK RAJ S
REG NO: 212222240023

```
class VacuumCleanerAgent:
    def init(self):
        self.location = 0  # Current location of the vacuum cleaner
        self.environment = ['Clean', 'Dirty', 'Clean']  # Example environment, you can customize as needed

    def sense(self):
        """Sense the current location"""
        return self.environment[self.location]

    def act(self, percept):
        """Act based on the percept"""
        if percept == 'Dirty':
            self.clean()
        else:
            self.move()

    def clean(self):
        """Clean the current location"""
        print("Cleaning...")
        self.environment[self.location] = 'Clean'

    def move(self):
        """Move to the next location"""
        print("Moving...")
        self.location = (self.location + 1) % len(self.environment)


# Main function to test the agent
def main():
    agent = VacuumCleanerAgent()
    print("Initial environment:", agent.environment)
    for _ in range(len(agent.environment)):
        percept = agent.sense()
        print("Percept:", percept)
        agent.act(percept)
    print("Environment after cleaning:", agent.environment)


if __name__ == "__main__":
    main()
```
<h3>OUTPUT</h3>
![photo_2024-02-27_14-18-41](https://github.com/DEEPAK2200233/19AI405ExpNo1/assets/118707676/9bd26950-8fa2-4540-987f-23221a06e0ab)


<h3>RESULT</h3>
The Program is excuted successfully.

