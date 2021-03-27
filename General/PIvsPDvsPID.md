1.) PI controller -
Advantages - Zero steady state error, Stability and Maximum peak overshoot is better than Integral only Controller.
Disadvantages - We cannot use PI controller for slow moving Process variables.
Application - Majority of the speed control applications use PI control action. Eg. Speed control of motors, generators, turbines etc.

NOTE:- PI control is definitely faster than only Integral action, but it may or may not be faster than Proportional only controller.

2.) PD controller
Advantages- Stability increased, Maximum peak overshoot decreased, Settling time decreases.
Disadvantages - Steady state error is not zero, cannot be used for fast moving process variables like flow, pressure., highly affected by external noise... A PD controller is analogous to a HPF along with aplifier.. This it aplifies high freq noise if present.

PD controllers are most widely used in temp control applications.
NOTE:- extra care has to be taken for set point changes in a PD controller to avoid a derivative kick.

3.) PID Controller
Advantages - steady state error is zero, moderate peak overshoot, moderate stability, can be used for controlling both fast and slow process variables.
Disadvantages - cost is high, Complexity and tuning, design complexity.
