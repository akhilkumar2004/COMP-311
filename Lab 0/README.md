# COMP 311: Lab 0

The goal of this lab is to get comfortable with the basic conventions of circuit diagrams, such as power, ground, wires, mechanical switch, and light emitting diode (LED). At the end, you should be comfortable with

- designing and testing simple circuits using the Digital software application and
- submitting your solution to Gradescope.

## 1. Clone this repo to your machine

```
git clone <repo_name>
``` 

## 2. Install Digital
Digital is a circuit design and simulation software. A Java Runtime Environment (at least JRE 8) is required to run Digital. You should already have one if you're using the same computer you used in COMP 210 or COMP 301. If not, please search online for installation instructions for your specific OS and install. **Make sure it can be run from the command line, and check the version with `java --version`**.

Follow the instructions on the [Digital](https://github.com/hneemann/Digital) GitHub page for downloading and running the software program (no installation required). In short, you simply download the .zip file, unzip it, and run the software.

### Windows users

To start Digital, simply double click the downloaded `Digital.exe` executable file.

### macOS/Linux installation

To start Digital, open a terminal and run `Digital.jar` with

```
java -jar PATH/TO/Digital.jar
```

#### Potential bug for macOS/Linux

If you encounter an uncommon bug where the Open menu does not display `.dig` files, you can open `.dig` files by passing them as a command-line argument. For example, if you want to open the file `~/circuit.dig`, run `java -jar Digital.jar ~/circuit.dig`. You can drag a file from Finder to the terminal to automatically paste its absolute path.

To easily start Digital without having to type the path to `Digital.jar`, you can alias the command. Run `echo "alias digital=\"java -jar $ABSOLUTE_PATH_TO_DIGITAL_JAR\"" >> $HOME/.zshrc`, replacing `$ABSOLUTE_PATH_TO_DIGITAL_JAR` with your **absolute** path to `Digital.jar`. If your default shell is bash (check with `echo $SHELL`), then you'll want to use `.bashrc` instead. **Restart your terminal**.

You'll now be able to type `digital` or `digital <file>` from any directory to run Digital.

## 3. Digital Tutorial
Complete the provided tutorial. It should pop up the first time you open Digital. If the tutorial does not show up, go to **Help > Documentation** and follow the steps on pages 6-13.

The tutorial references k-maps. We will learn those soon.

### Note for macOS users
If `control-click` does not work for you, try two-finger tap.

## 4. Read Instructions for Digital

Within Digital, you can access a useful help document by clicking **Help > Documentation**. We recommend reading

- `Section 1`: How to navigate through the program and create simple circuits.
- `Secion 3.2`: LED with two connections.
- `Sections 6.1 and 6.2`: Ground and voltage supply or **power**.
- `Section 13.1`: Mechanical on/off switch.

## 5. LED Circuit

We have provided you with a simple circuit that allows you to use a switch to turn an LED on and off. When the LED is on, it is red. When it is off, it is black. To view this circuit, open the file `Lab00a.dig`. We will be using this cicuit to familiarize ourselves with Digital.

When you first open the file, you are in edit mode. To switch to simulate mode, press the triangular `play` button at the top. Now you can open and close the switch. When the switch is closed, the circuit should light up. Carefully inspect how the LED is wired and notice which components represent power (logic 1) and which represent ground (logic 0). 

The color of the wire signifies the value of the signal on the wire - light green is logic 1 (high state), dark green is logic 0 (low state), gray is high Z state (basically means the signal is undefined).

## 6. Mechanical AND gate

In this exercise, you are given two switches, an LED, power, and ground. Your job is to use wires to connect these components such that the LED only turns on when both switches are closed. 

We call this a **“mechanical AND gate,”** because the LED output represents the logical AND of the two switches.

| switch 1      | switch 2 | LED    |
| :---:       |    :----:   |         :---: |
| 0 (open)     | 0 (open)      | 0 (off)   |
| 0 (open)   | 1 (closed)        | 0 (off)      |
| 1 (closed)     | 0 (open)      | 0 (off)   |
| 1 (closed)   | 1 (closed)        | 1 (on)      |

Please do *not* delete or rename the switches (moving them is fine, though unnecessary). The autograder uses the component names `switch1` and `switch2` during testing. In future Digital labs, you will add names to components yourself, but this is already done for you in this lab.

<details>
  <summary>Click here for instructions if you've already deleted or renamed the switches
  </summary>
If you have already deleted them, then either revert changes in your git repo or add the switches back. If you add them back, you need to right-click the component to bring up options (on macOS, either use a mouse or go to your settings, search for "Trackpad", and make sure "Secondary click" is set to "Click or Tap with Two Fingers"), select "Advanced", check "Switch behaves like an input", and rename them to the proper names.

![image](https://user-images.githubusercontent.com/55986131/149873493-8da11454-750e-466d-b3ae-31c0fd0025d6.png)
</details>

Construct your design in Digital using the `Lab00b.dig` file. You should only need to add wires and delete wires, not add any additional components. Verify that your design works in Digital by using the triangular `play` button to simulate the circuit. The LED should light up only when both switches are in the closed position.

**Note:** It is highly unlikely but possible to create a mechanical **AND** gate design that seems to work according to the first paragraph of this section yet fails the autograder tests. This would occur if you wire the circuit in a specific improper way (again, most people will not encounter this). These designs don't pass the tests because they are considered incorrect.

## Submission

Assignments will be submitted through [Gradescope](https://www.gradescope.com).

You should already be enrolled in the COMP 311 course on Gradescope. If you are not enrolled, please email the instructor.

1. Commit and push your changes to your Lab 0 GitHub repo. (The only file you should have changed is `Lab00b.dig`).
2. Go to the COMP 311 course in Gradescope and click on the assignment called **Lab 0**.
3. Click on the option to **Submit Assignment** and choose GitHub as the submission method. You may be prompted to sign in to your GitHub account to grant access to Gradescope. When this occurs, grant access to the Comp311 organization.
4. You should see a list of your 311 repositories. Select the one named **lab-0-yourname** and submit it.
5. Your assignment should be autograded within a few seconds and you will receive feedback.
6. If you receive all the points, then you have completed this lab assignment! Otherwise, you are free to keep pushing commits to your GitHub repository and submit for regrading up until the deadline of the lab.
