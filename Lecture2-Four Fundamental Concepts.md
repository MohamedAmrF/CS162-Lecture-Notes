# Four Fundamental OS Concepts

## 1) __Thread__
> Single unique exectution context  

<br/>  

- program counter, registers, execution flags, stack , memory states.

- A thread is **exectuing** on a processor when it is ***resident*** in the processor registers.

- A thread is ***suspended*** when it is ***note loaded*** in the registers.

- **Threads** are virtual cores.

- Illusion of multiple processes comes from running many processes after each other.

- Where is the "Thread" ?
    - Either on
        - physical core itself
    - or
        - saved in the memory- called ***Thread Control Block***.
- What triggers the context switch between the threads ?
    - Timers, I/O, ... etc.

### __Thread Control Block__
- Holds contents of Registers + some other info.
- assume for now that they are stored in the kernel.

### __Thread vs process:__
> Thread has a ***protection state*** associated with it.

### **The Instruction Cycle**: 
- Fetch / Decode / Execute

<br/> <br/>

##  __2) Address Spaces :__
> Set of accessible addresses + states associated with them.

- Simple protection
    - base and bound

## __3) Process :__
>Execution environment with restricted rights.
- owns memory
- encapsulate one or more threads sharing process resources.
- ***Application program*** executes as process.

__Why Processes?__
- protected from each other
- os protected from them
- Tradeoff between protection adn efficiency.   
    - communication is easy within process
    - harder between processes.
- **Reliability**: bugs overwrite memory allocated only for them
- **Security**: can't read or write other processes data
- **Fairness**: enforce shares od disk
## __4) Dual mode operation :__
    1) Kernel mode
    2) User mode

How to Enter Kernel Mode?
1) System call
2) Interrupt
3) Trap (Exception)
    - segmentation fault, divide by zero, ...

