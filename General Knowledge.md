1. how is static keyword different in C++ vs C? 
	1. in C: the function/ variable is only accessible via functions inside the same sourcefile, comparable to private funcs/members in C++
	2. in C++: the methods are not members of a class instance, but are more like functions + namespace, and static class members are shared across all instances of the class 
		1. C++ also has both uses of static
2. what is the difference in passing something by reference and passing something by a pointer?  
	1. pass by reference: 
		1. to pass the reference of an argument in the calling function to the corresponding formal paramteter of the called function 
		2. called function can modify the value of the argument using its reference passed in
		3. to modify a reference that's const, we need to un-const it. this is done by using the const_cast operator
		4. pass by reference is usually more efficient than pass by value because it does not copy the args. when you call a func on the actual arg, then it actually has to go through the dance of really reading or writing the values from mem 
	2. pass by pointer: 
		1. to pass a pointer argument in the calling function to the corresponding formal parameter of the called function
		2. the called function can modify the value of the variable to which the pointer argument points
		3. when you pass something by pointer, a copy of the **pointer** is passed to the function, and if you modify the pointer inside the called function, then you only modify the copy, and the original points to the same thing as it always did (remains unchanged)
		4. use pass by pointer if you want to modify the argument value inside the called function, otherwise we can use pass by value
3. how is const used differently in C++ vs C? 
	1. c++ :
		1. internal linkage by default
		2. can be used as compile time values 
		3. pointers to string literals must be a char const*
	2. c
		1. external linkage by default
		2. cannot be used as compile time values
		3. pointers to string literals can be char*
4. what is an example of the virtual keyword
	1. by default, c++ matches a function call with the correct function definition at compile time
		1. this is static binding
	2. you can specify that the compiler match a function with the correct definition at run time instead
		1. this is called dynamic binding
	3. you can declare a function as "virtual" if you want the compiler to use dynamic binding for that specific function
	4. the keyword tells the compiler that it should choose the appropriate definition of f() not by the lvalue ref, but by the type of object that the lvalue reference refers to.
		1. because of this, a virtual function is a member function that you can redefine for other classes, and can ensure that the compiler will call the redefined virtual function for an object of the corresponding derived class, even if that function is called with a pointer or a reference to the base class of the object itself
	5. the access for a virtual function is specified only when it is declared
	6. the access rules for a virtual function are not affected by the access rules for the function that later overrides the virtual function 
	7. if a virtual function is called with a pointer or reference to a class object, the type of the class object is not used to determine the access of the virtual function 
		1. instead, we use the type of the **pointer** or **reference
	8. write some simple classes like Shape, Square, Circle, etc
6. microcontroller specifics:
	1. microcontrollers are compact integrated circuits that serve as the "brains" of embedded systems, and control specific functions or devices. they're usually used in applications that require real-time control 
	2. microcontroller vs microprocessor: 
		1. microprocessors support versatile computing operations in personal computers and enterprise servers. 
			1.  clock speed: provide high speed and robust capacities when it comes to clock speed for many diff applications
			2. circuit size: cannot operate on its own, and relies heavily on external parts like communication chips, I/O ports, RAM and ROM
				1. because of this, a microP circuit consists of an address and data bus connecting many peripherals and memory chips
				2. requires considerable amount of space 
			3. power consumption: since they run at a higher speed, they consume more power and usually need an external power supply, and because of this, a system that relies on a microprocessor overall will have higher power demands
			4. operating system: microprocessors usually need an OS to provide functionality. without an OS users would have to directly instruct the microP on what to do
			5. connectivity: microP usually handle more diverse communication technologies than microcontrollers
				1. for ex, processing USB 3.0 or etheret without another processor
		2. microcontrollers allow embedded systems to analyze and respond to inputs in real time 
			1. clock speed: clock speeds for microcontrollers have steadily increased throughout recent decades, but its significantly slower than a microprocessor. however, it can still operate optimally within its dedicated scope of application 
			2. circuit size: since it is a simpler circuit, it's also often a much more space saving design
			3. power consumption: microcontrollers are designed to act really well and operate extremely efficiently with minimal power, and most microcontrollers also have further power saving features like power saving mode when not actively processing data 
				1. they can also turn off internal periphersals not in use 
				2. this makes them ideal for building a low power application that runs on stored power alone
			4. operating system: microcontrollers dont really need an OS, but there are some OS that exist for helping mid and high range microcontrollers to run more efficiently 
			5. connectivity:  microcontrollers usually need a special processor for high speed data connectivity
	3. internals
		1. CPU: heart of the microcontroller <3, where data processing and computation happen, executes instructions stored in memory to perform tasks
			1. microcontroller CPUs are usually low-power and optimized for control tasks rather than raw processing speed
			2. usually use RISC architectures like ARM Cortex-M for efficiency and simplicity
		2. Memory(ROM,RAM, and EEPROM): for storing program code, data, and persistent information
			1. Read-Only Memory (ROM): stores program code and is non volatile, so it retains the data even if the power is removed. 
				1. flash memory is the most common ROM type and allows for easy reprogramming 
			2. Random Access Memory (RAM): used for temporary storage of variables and data during program execution, and is volatile, meaning that data is lost when power is turned off 
			3. Electrically Erasable Programmable ROM (EEPROM): non volatile memory that stores small amounts of data that need to be preserved between power cycles, such as user settings
		3. I/O Ports: 
			1. Digital IO: pins can be set to high or low states to control LEDs, switches, etc.
			2. Analog IO: some microcontrollers have analog input pins connected to ADC or DAC converters to read varying voltage levels (eg for sensors)
			3. Peripheral Interfaces: microcontrollers also support protocols like I2C, SPI, and UART, which allow connection to a wide variety of components like displays, storage modules, etc 
		4. Timers & Counters: create delays, measure intervals, generate waveforms, and control the timing of events
			1. timers: can be configured to trigger at regular intervals, which enable tasks like blinking LEDs or sampling sensors
			2. Counters: count pulses for events like external signals or clock cycles and can be used in applications like frequency measurement 
			3. watchdog timer: monitors the system and resets the microcontroller if the program becomes unresponsive, which then also improves reliability 
		5. Analog to Digital converter: 
			1. converts analog signals from sensors into digital data that the CPU can process
				1. have a certain resolution ( 8-bit, 10-bit, 12-bit, etc) that determines the precision of the conversion 
				2. sampling rate: determines how frequently the ADC can sample an analog signal, crucial for realtime applications
		6. Digital to Analog converter: 
			1. converts digital values back into analog signals, used usually in audio processing, motor control, and other applications that need precise analog output
		7. Clock Source (Oscillator):  microcontrollers need a clock signla to synchronize operations 
			1. internal oscillator: many microprocessors have an internal clock
			2. external crystal oscillator: external clocks can provide more accurate timing, and are usually required for tasks like precise communication protocols
			3. clock frequency affects processing speed
		8. Communication modules: 
			1. UART: allows serial communication between devices, usually used for debugging or connecting to other devices 
			2. SPI: a fast, synchronous protocol used for high speed communication with devices like sensors, displays, and SD cards
			3. I2C: a two wire, slower protocol suitable for communication with multiple peripherals on the same bus 
			4. CAN: common in automotive applications for communication between ECUs
		9. Interrupt controller: interrupts are signals that temporarily halt the CPU to address time sensitive events. they allow the microcontroller to respond quickly to external or internal events without continuously polling
			1. external interrupt: triggered by external events like pressing a buttong
			2. internal interrupt: caused by internal events, like a timer overflow
			3. interrupt vector table: maps specific interrupts to their handler functions
		10. Power management: 
			1. sleep modes: reduce power consumption by disabling certain components when not needed, and allows the microcontroller to "wake up"  on specific events like a timer or interrupt 
			2. low-power oscillators: used to keep the microcontroller running in low-power mode with a minimal clock frequency
		11. special function registers: 
			1. registers that control the microcontroller's peripherals, IO, and configuration settings. they allow the program to interact directly with hardware by setting flags, configuring modes, and monitoring statuses
	4. ISR: Interrupt service Routine, a special function that's executed in response to an interrupt
	5. pipelines: pipelining is a technique that's used to improve instruction throughput by breaking down instruction execution into several stages. each stage performs part of the instruction's execution, which then allows multiple instructions to be performed simultaneously like an assembly line, and can increase efficiency and speed of a processor, because it lets the CPU process a new instruction every clock cycle
		1. 5 stages: 
			1. fetch: cpu fetches the next instruction from memory
			2. decode: the cpu decodes the fetched instruction to determine what operation it needs to perform and which resources are required
			3. execute: the actual operation happens to the data
			4. memory access: if reading or writing is involved, or RAM is involved, this is where it comes in 
			5. write back: the operation result is written back to a register or memory
	6. peripherals: extend the microcontroller's capabilities by providing interfaces to interact with external devices or perform specific functions within the microcontorller itself. some common peripherals include: 
		1. General purpose IO (GPIO) pins: a basic interface for controlling external components like LEDs, buttons, and sensors 
			1. input mode: reads data from external sources, for ex, a button can send a high or low signal to indicate whether its pressed 
			2. output mode: sends signals to external devices, like sending a high signal to go turn on an LED
			3. alternate functions: GPIO pins can also sometimes have multiple functions, like being reassigned to other peripherals 
		2. Timers & Counters: crucial for managing timing-related tasks without heavy CPU involvement 
			1. timers: generate precise time delays or periodic events, and are often used to create delays, measure intervals, or generate waveforms 
			2. counters: count external events or pulses
			3. Pulse Width modulation(PWM) generation: some timers can generate PWM signals for tasks like motor speed control or LED brightness 
7. RTOS specific questions
	1. realtime: having timeless requirements, typically in the form of deadlines that can't be missed ; realtime operating system: an operating system that is designed specifically for use in read time systems; real time system: any computer system that has timeless requirements. aka if a late answer is as bad, or even worse, than a wrong answer 
	2. mutex vs semaphore
		1. Mutex: mutual exclusion object, and is mainly used to provide mutual exclusion to a specific portion of the code so that the process can execute and work with a particular section of the code at a particular time. it enforces strict ownership, so only the thread that locks the mutex can unlock it, and because of this it is specifically used for locking a resource to make sure that it's only accessible by one thread at a time. this strictness is also what prevents mutexes from being used for signaling between threads, and instead makes it desireable for ensuring that a resource is accessible only by one thread at a time 
			1. uses priority inheritance to avoid priority inversion issues, which keeps higher priority processes in the blocked state for the minimum possible time
			2. advantages: no race conditions, data remains consistent, helps maintain integrity, simple locking mechanism 
			3. disadvantages: if a thread falls asleep or gets preempted  by a high priority process, no other thread can enter into the critical section, and can lead to starvation, there's no other mechanisms to lock/unlock a critical section, and implementation of the mutex can led to busy waiting, which can waste CPU cycles
			4. producer-consumer problem: a mutex provides mutual exclusion, and either the producer or the consumer can have the key (mutex) and then proceed with their work, and as long as the buffer is filled by the producer, then the consumer needs to wait and vice verse; so at any point in time, only one thread can work with the entire buffer.
		2. Semaphore: a semaphore is a non-negative integer that's shared between several different threads, and works upon a signaling mechanism, which allows threads to control other threads. This is a less restrictive control mechanism, as any thread can invoke signal() and any other thread can invoke wait(), and there's no strict ownership in semaphores, so the thread that signals doesn't necessarily have to be the same one that waited. Semaphores are like traffic signals between threads, but a bit more chaotic and much less safe. This uses two main atomic operations for process synchronization: wait (P), signal (V)
			1. advantages: 
				1. multiple threads can access the critical section at the same time 
				2. semaphores are machine-independent
				3. only one process will access the critical section at a time, however, multiple threads are allowed
				4. semaphores need to be run over microkernel
				5. flexible resource management
			3. disadvantages: 
				1. has priority inversion 
				2. semaphore operations (wait, signal) must be implemented in the correct manner to avoid deadlock
				3. leads to a loss of modularity, so semaphores can't be used for large-scale systems
				4. prone to programming errors, which can lead to deadlock or violation of mutual exclusion property
				5. 
	3. scheduling policies
	4. context switches
9. Linux questions
	1. ssh 
	2. vim 
	3. bash/python
	4. git 
	5. gcc
	6. man pages?
10. systems knowledge: 
	1. read()
	2. write()
	3. poll()
	4. sockets
	5. fork()
	6. system calls: calls that a program makes to the system kernel to provide the services which the program does not have direct access, for ex: access to IO devices
		1. File Descriptor: an integer that uniquely identifies an open file of the process
		2. File descriptor table: the collection of integer array indices that are file descriptors in which elements are pointers to file table entries, one unique table is provided in the OS for each process 
		3. File table entry: a structure in-memory surrogate for an open file, which is created when processing a request to open the file and these entries maintain a file position 
		4. standard file descriptors: when any process starts, that process file descriptor tables 0,1,2 open by default, and each of these three file descriptor references file table entry for a file named /dev/tty
		5. there are 5 main types of IO syscalls in C: 
			1. create() : int create(char * *filename*, mode_t *mode);
				1. takes in the name of the file you want to create, and the permissions of the new file 
				2. returns the first unused fd, which is usually 3 , and -1 if there's an error
				3. creates a new empty file on the disk and a table entry
			2. open(): int open (const char * *Path*, int *flags*);
				1. takes in the path to the file we want to open as an absolute path beginning with / if not in the same dir, or relative path without / and with extension if we are in the same directory
				2. there are also several flags that we can set to this action: 
					1. ![[Pasted image 20241105233118.png]]
			3. close(): int close(int fd); 
				1. takes in the fd, file descriptor, of the file that we want to close
				2. returns 0 if successful, or -1 if there's an error 
			4. read(): size_t read (int *fd*, void *  *buf*, size_t *cnt*);
				1. takes in the fd of the file we want to read, the buffer to read the data from, and cnt, the length of the buffer 
				2. returnsthe number of bytes read on success, 0 on reaching the end of the file, -1 on an error, and -1 on signal interrupt 
			5. write(): size_t write(int *fd*, void * *buf*, size_t *cnt*); 
				1. takes in the fd, the buffer to write data from, and the length of the buffer 
				2. returns the number of bytes written on success
				3. returns 0 when the end of the file is reached 
				4. returns -1 on an error 
				5. returns -1 if there's a signal interrupt 
	7. device drivers: a piece of software that enables communication between an OS or app and hardware or peripherals, basically a bridge between different parts of a computer and allows them to communicate and interact, generally through the computer bus
11. what is RAII? "Resource Acquisition Is Initialization"
	1. when an object is initialized, it acquires the resource that it needs (memory, file handle, network connection, etc,)
	2. RAII ensures that resources are released even if exceptions occur, which prevents leaks and maintains program integrity 
	3. makes automatic cleanup happen, keeping things nice and simple 
12. what is a constructor/destructor
	1. constructor: a constructor is a special method that's automatically invoked when an object class is first created, and is used to initialize the data members of new objects generally. Has the same name as the class or structure it is associated with, and constructs the values or provides data for the object that it's associated with. they do not have a return type and are usually declared in the public section of the class 
		1. default constructor: no parameters, and used to create an object with default names
		2. parameterized constructor: takes in parameters, and is used to create an object with specific initial values 
		3. copy constructor: takes a reference to another object of the same class and is used to create a copy of that object 
		4. move constructor: takes an rvalue reference to another object, and transfers resources from a temporary object 
	2. destructor: an instance member function that is invoked automatically whenever an object is going to be destroyed, the last function to be called before an object is destroyed 
		1. if memory is allocated by the object using new, the destructor must deallocate it using delete[]
13. when to call const/ destructor
	1. constructor: automatically called when an instance of the class is created
	2. destructor: doesn't really need to be called explicitly unless we're dealing with memory management and/ or whenever objects are deallocated / destroyed (?)
14. const: marks a variable's value as constant and that it is resistant to changes / edits made by the program, basically marks it as "read only"
15. static: 
16. public/private
17. what is an int? how many bytes? does it always have the same number of bytes? 
19. what is the mutable keyword?
	1. in C++, objects are considered mutable if their state can be modified after they are created, like variables, whose values can be updated throughout the program, as opposed to const variables, which cannot be changed
	2. the mutable keyword however, essentially overrides const, and allows us to modify a member variable of a class even when the object is declared as const, which can be useful for caching values or maintaining internal states that don't affect the object's logical constness
	3. basically allows a particular data member of a const function to be modified, and allows the differentiation of bitwise const and logical const 
		1. logical const is is when an object doesn't change in a way that's visible to the public interface
	4. need to be careful about the usage, since it can competely destroy the constness of a function if used incorrectly, basically making it useless and possibly having negative affects on functionality. 
20. what does the C keyword volatile do?
	1. volatile is a qualifier that's applied to a variable when it's declared, which is meant to tell the compiler that the value of a var may change at any time
	2. to declare a variable as volatile, we need to add "volatile" before the data type of the variable 
22. when does it make sense to use a volatile const variable?
	1. it's used in situations where a variable's value may change outside the program's control, but should not be modified by the code itself, such as in : 
		1. microcontrollers: in embedded systems, a common scenario for volatile const is with memory-mapped hardware registers that are read-only but may change unexpectedly due to external factors . for ex: peripherals like ADCs , although should be constant, can update randomly from the hardware
23. is ++i or i++ faster?
	1. usually preincrement (++i) is slightly faster than i++, particularly in C++ since in preincrementation, the item is first incremented, and then the value is returned, so it increments i directly and does not need to create a temporary copy, whereas in post increment, i++, a temporary copy of i is created, then the original is incremented, and then the copy (nonincremented) is returned, which tends to be slower with more complex data types 
24. what is RTOS priority inversion and one way to resolve it?
	1. priority inversion is when a high priority task is blocked by a lower priority task, which is then also waiting on an even lower priority task, which can ultimately lead to missed deadlines in time sensitive applications 
	2. priority inheritance is one way to solve this: when a lower priority task holds a resource that a high priority task needs, the lower priority task temporarily inherits the priority of the higher priority task, which allows the lower task to finish its work and release the resource more quickly, and then the priorities switch back. 
25. Serial Peripheral interface (SPI) : facilitates short-distance communication between a microcontroller and one or more peripheral integrated circuits, a de facto standard
26. Inter-Integrated Circuit (I2C): a simple two-wire serial protocol that's used to communicate between two devices or chips in an embedded system
	1. two lines, SCL and SDA, SCL is used for the clock and SDA is used for data
28. bitwise operations 
	1. mask on
	2. mask off 
	3. shifts
	4. etc
29. embedded linux misc
30. APQP product dev cycle
32. [https://rmbconsulting.us/publications/a-c-test-the-0x10-best-questions-for-would-be-embedded-programmers/](https://rmbconsulting.us/publications/a-c-test-the-0x10-best-questions-for-would-be-embedded-programmers/)
33. common chip to chip communication protocols
34. what chips are you familiar with?
35. what framework, HALs, or SDKs have you used?
36. sorting questions
37. what is DMA, when to use it
38. what is a vector interrupt controller
39. have you used RTOS? Which?
40. when to use RTOS
41. mutex and semaphore questions
42. have you used embedded linux?


**Embedded C Questions**  
- Describe how to multiply two 256-bit numbers using any 32-bit processor without FPU or special instructions. Two or more methods?  
- When do you use memmove() instead of memcpy() in C? Describe why.  
- When is the best time to malloc() large blocks of memory in embedded processors?  
- Describe an alternate approach if malloc() isn't available or you desire not to use it, and describe some things you will need to do to ensure it safely works.  
- Design a circular queue for an embedded system. Applications of the circular queue in Camera and AR applications.  
- What are the potential problems using malloc in multithreaded settings assuming no data race nor hardware issue?  
- malloc - implicit linked list-based implementation  
- How do we find out if the stack is growing upward or downward?  
- Implement a DMA driver.  
- Implement Memory pool allocator in C without using built-in malloc() and free() functions.  
- Implement an aligned malloc function using the built-in malloc function.  
- How to find the size of flexible array members?  
- How to implement an efficient memset API?  
- Apply a caller-provider function for each entry in an array.  
**Bit Manipulation**  
- Find the maximum of two numbers without using any if-else statements, branching, or direct comparisons.  
- implement a Count Leading Zero (CLZ) bit algorithm, but don't use the assembler instruction. What optimizations to make it faster? What are some uses of CLZ?  
- Write a function that swaps the highest bits in each nibble of the byte  
- Given an 8-bit pattern, find the pattern in the bitstream and return the bit offset.  
- What is the size of the integer variable on 32bit and 64bit machines?  
- Write a function that swaps the highest bits in each nibble of the byte.  
- Write a function to convert Big Endian to Little Endian System.  
- How to read a 128-bit timestamp on 64-bit architecture?  
**Computer Architecture(MCU) Questions**  
- When building an embedded system, how will you decide when to use a microcontroller and when to use a microprocessor?  
- How is a microcontroller used to determine the high-voltage level frequency on a bus?

- Write a code that causes TLB misses for each instruction.  
- Dhrystone MIPS (Million Instructions per Second) - What is it? How is measured for current CPUs?  
**Real-Time OS Questions**  
- Which real-time software metrics are the most important, according to you?  
- What are the pros and cons of using a real-time OS on a mid-range micro-controller?  
- How do event-driven real-time systems overcome the bottlenecks of systems with shared concurrency systems?  
- How do test-and-set instructions work and their usage in the locking mechanism for synchronization? 

1) Which endianness is: A) x86 families. B) ARM families. C) internet protocols. D) other processors? One of these is kind of a trick question.

2) Explain how interrupts work. What are some things that you should never do in an interrupt function?

3) Explain when you should use "volatile" in C.

4) Explain UART, SPI, I2C buses. Describe some of the signals in each. At a high-level describe each. Have you ever used any? Where? How? What type of test equipment would you want to use to debug these types of buses? Have you ever used test equipment to do it? Which?

5) Explain how DMA works. What are some of the issues that you need to worry about when using DMA?

6) Where does the interrupt table reside in the memory map for various processor families?

7) In which direction does the stack grow in various processor families?

8) Implement a Count Leading Zero (CLZ) bit algorithm, but don't use the assembler instruction. What optimizations to make it faster? What are some uses of CLZ?

9) What is RISC-V? What is it's claimed pros or cons?

10) List some ARM cores. For embedded use, which cores were most commonly used in the past? now?

11) Explain processor pipelines, and the pro/cons of shorter or longer pipelines.

12) Explain fixed-point math. How do you convert a number into a fixed-point, and back again? Have you ever written any C functions or algorithms that used fixed-point math? Why did you?

13) What is a pull-up or pull-down resistor? When might you need to use them?

14) What is "zero copy" or "zero buffer" concept?

15) How do you determine if a memory address is aligned on a 4 byte boundary in C?

16) What hardware debugging protocols are used to communicate with ARM microcontrollers?

17) What processor architecture was the original Arduino based on?

18) What are the basic concepts of what happens before main() is called in C?

19) What are the basic concepts of how printf() works? List and describe some of the special format characters? Show some simple C coding examples.

20) Describe each of the following? SRAM, Pseudo-SRAM, DRAM, ROM, PROM, EPROM, EEPROM, MRAM, FRAM, ...

21) Show how to declare a pointer to constant data in C. Show how to declare a function pointer in C.

22) How do you multiply without using multiply or divide instructions for a multiplier constant of 10, 31, 132?

23) When do you use memmove() instead of memcpy() in C? Describe why.

24) Why is strlen() sometimes not considered "safe" in C? How to make it safer? What is the newer safer function name?

25) When is the best time to malloc() large blocks of memory in embedded processors? Describe alternate approach if malloc() isn't available or desired to not use it, and describe some things you will need to do to ensure it safely works.

26) Describe symbols on a schematic? What is a printed circuit board?

27) Do you know how to use a logic probe? multimeter? oscilloscope? logic analyzer? function generator? spectrum analyzer? other test equipment? Describe when you might want to use each of these. Have you hooked up and used any of these?

28) What processors or microcontrollers are considered 4-bit? 8-bit? 16-bit? 24-bit? 32-bit? Which have you used in each size group? Which is your favorite or hate?

29) What is ohm's law?

30) What is Nyquist frequency (rate)? When is this important?

31) What is "wait state"?

32) What are some common logic voltages?

33) What are some common logic famlies?

34) What is a CPLD? an FPGA? Describe why they might be used in an embedded system?

35) List some types of connectors found on test equipment.

36) What is AC? What is DC? Describe the voltage in the wall outlet? Describe the voltage in USB 1.x and 2.x cables?

37) What is RS232? RS432? RS485? MIDI? What do these have in common?

38) What is ESD? Describe the purpose of "pink" ESD bags? black or silvery ESD bag? How do you properly use a ground strap? When should you use a ground strap? How critical is it to use ESD protections? How do you safely move ESD-sensitive boards between different parts of a building?

39) What is "Lockout-Tagout"?

40) What is ISO9001? What is a simple summary of it's concepts?

41) What is A/D? D/A? OpAmp? Comparator Other Components Here? Describe each. What/when might each be used?

42) What host O/S have you used? List experience from most to least used.

43) What embedded RTOS have you used? Have you ever written your own from scratch?

44) Have you ever implemented from scratch any functions from the C Standard Library (that ships with most compilers)? Created your own because functions in C library didn't support something you needed?

45) Have you ever used any encryption algorithms? Did you write your own from scratch or use a library (which one)? Describe which type of algorithms you used and in what situations you used them?

45) What is a CRC algorithm? Why would you use it? What are some CRC algorithms? What issues do you need to worry about when using CRC algorithms that might cause problems? Have you ever written a CRC algorithm from scratch?

46) Do you know how to solder? Have you ever soldered surface mount devices?

47) How do you permanently archive source code? project? what should be archived? what should be documented? have you ever written any procedures of how to archive or build a project? How about describing how to install software tools and configuring them from scratch on a brand new computer that was pulled out of a box?

48) What issues are a concern for algorithms that read/write data to DRAM instead of SRAM?

49) What is the "escape sequence" for "Hayes Command Set"? Where was this used in the past? Where is it used today?

50) What is the "escape character" for "Epson ESC/P"? Where is this used?

51) After powerup, have you ever initialized a character display using C code? From scratch or library calls?

52) Have you ever written a RAM test from scratch? What are some issues you need to test?

53) Have you ever written code to initialize (configure) low-power self-refreshing DRAM memory after power up (independent of BIOS or other code that did it for the system)? It's likely that most people have never done this.

54) Write code in C to "round up" any number to the next "power of 2", unless the number is already a power of 2. For example, 5 rounds up to 8, 42 rounds up to 64, 128 rounds to 128. When is this algorithm useful?

55) What are two of the hardware protocols used to communicate with SD cards? Which will most likely work with more microcontrollers?

56) What issues concerns software when you WRITE a value to EEPROM memory? FLASH memory?

57) What is NOR-Flash and NAND-Flash memory? Are there any unique software concerns for either?

58) Conceptually, what do you need to do after reconfiguring a digital PLL? What if the digital PLL sources the clock for your microcontroller (and other concerns)?

59) What topics or categories of jokes shouldn't you discuss, tell, forward at work?

60) Have you ever used any power tools for woodworking or metalworking?

61) What is a common expression said when cutting anything to a specific length? (old expression for woodworking)

62) Have you ever 3D printed anything? Have you ever created a 3D model for anything? List one or more 3D file extensions.

63) Do you know how to wire an AC wall outlet or ceiling light? Have you ever done either?

64) Have you ever installed a new hard drive / RAM / CPU in a desktop computer?

65) Have you ever installed Windows or Linux from scratch on a computer that has a brand-new hard drive?

66) Have you ever "burned" a CD-R or DVD-R disc? Have you ever created an ISO image of a CD or DVD or USB drive or hard drive?

67) Have you ever read the contents of a serial-EEPROM chip from a dead system (though EEPROM chip is ok)?

68) Have you ever written data to a serial-EEPROM chip before it is soldered down to a PCB?

69) How do you erase an "old school" EPROM chip? (has a glass window on top of the chip)

70) Describe any infrared protocols, either for data or remote controlling a TV.

71) What is the most common protocol is used to communicate with a "smart card"? Have you ever written any software to communicate with a "smart card" in an embedded product?

72) What is I2S? Where is it used? Why might you want to use I2S in an embedded system? Have you ever used it?

73) What is CAN, LIN, FlexRay? Where are they used? Have you ever used any?

74) What is ARINC 429? Where is it commonly used? Have you ever used it?

75) What in-circuit debuggers or programmers have you used? Which one do you like or hate?

76) Do you know any assembler code? For which processor? What assembler code is your favorite or hate? Have you ever written an assembler from scratch?

77) What is "duff's device"? Have you ever used it?

78) What is dual-port RAM? Why would it be useful in some embedded systems? What concerns do you need to worry about when using it? Have you ever used it? How?

79) Have you ever soldered any electronic kits? Have you ever designed your own PCB(s)? Describe. What is a Gerber file?

80) If you create a circular buffer, what size of buffer might optimized code be slightly faster to execute? why?

81) Describe how to multiply two 256-bit numbers using any 32-bit processor without FPU or special instructions. Two or more methods?

### Specific Resources

|Concept|Resources|
|:--|:--|
|C|[K&R](https://en.wikipedia.org/wiki/The_C_Programming_Language), the canonical C handbook, and a relatively quick read. ["Modern C" by Gustedt](http://icube-icps.unistra.fr/index.php/File:ModernC.pdf) for a more in depth, and modern, take.|
|Testing|"Test Driven Development for Embedded C" by Grenning|
|Operating Systems|"Operating Systems" by Silberschatz. ["Operating Systems: Three Easy Pieces" by Arpaci-Dusseau](http://pages.cs.wisc.edu/%7Eremzi/OSTEP/)|
|RTOS|A good operating systems textbook will be a great starting point. Checkout this [FreeRTOS Tutorial](https://www.freertos.org/tutorial/), and I've also heard good things about the "Modern Embedded Systems Programming" YouTube channel. [Real-Time Bluetooth Networks - Shape the World](https://www.edx.org/course/real-time-bluetooth-networks-shape-the-world)|
|I2C, UART, SPI|There are great articles on [Sparkfun](https://learn.sparkfun.com/tutorials/serial-communication/all) and [Adafruit](https://learn.adafruit.com/circuit-playground-express-serial-communications/what-is-serial-communications).|
|Sensors & Actuators|The [Robogrok](http://www.robogrok.com/) robotics course Youtube videos have a great, newbie friendly introduction to robotics, sensors, actuators, and PID control.|
|Linux Kernel Development|I frequently see "Linux Kernel Development" by Love as recommended|
|Microcontrollers|[Embedded Systems Rule the World](http://users.ece.utexas.edu/%7Evalvano/Volume1/E-Book/)|
|Bluetooth / Wifi / IEEE 802.11|[Real-Time Bluetooth Networks - Shape the World](https://www.edx.org/course/real-time-bluetooth-networks-shape-the-world)|

**Other General Resources I've found helpful:**

The "Making Embedded Systems" book by Elecia White ([/u/logicalelegance](https://old.reddit.com/u/logicalelegance)) -- a great introduction to the basics of embedded systems, and does a good job of being an easy read for newbies.

[Embedded.fm Podcast](https://embedded.fm/). Great podcast hosted by the above author.

[Embedded Artistry](https://embeddedartistry.com/). Good articles.

[The Ganssle Group](http://www.ganssle.com/). Good articles.

[Barr Group](https://barrgroup.com/). Good articles.

[The Amp Hour](https://theamphour.com/). Hardware focused podcast.

[Adafruit](https://learn.adafruit.com/). The 'working out of the box' hardware paired with newbie friendly tutorials are a nice starting point. Professional development kits and datasheets are oriented towards people who've already worked on similar systems, so there is quite a bit of assumed context someone new to the field doesn't have.

## More Interview Questions

- What is static?
- What is volatile?
- How does an interrupt work?
- What programming practices should typically be avoided in embedded systems, and why?
- Basic circuits questions: Ohms law. Voltage Dividers. Series and Parallel Resistors.
- Compare and contrast I2C, UART, and SPI
- How does an ADC work? How about a DAC?
- Compare and contrast Mutex and Semaphores
- Linked List algorithm questions
- String manipulation algorithm questions
- Bit manipulation algorithm questions
- Tell me about a hardware issue you debugged.
- Why would you use an RTOS?
- How does an OS manage memory?



Some questions for larger embedded systems might also be a good idea:

83. What is a DSP?

84. What are virtual and physical addresses? What is a MMU?

85. Describe different types of Cache. When do you need to flush the cache, when to invalidate cache?

86. What is SIMD?

87. What is a Mailbox register?

88. What is a Cacheline?

89. What is a Mutex?

90. What is Scatter-Gather DMA? What is Ping-Pong DMA?

91. What is WCET and where does it matter?

92. What is Lockstep execution?



- implement memcpy (followed by "now optimize it")
    
- implement a circular buffer
    
- determine whether a given number is a power of two (without using arithmetic operators, if you want)
    
- rarely some basic assembly stuff, really just looking for out loud discussion of addressing
    
- what is a segmentation fault (this one has lead to some interesting discussions), what other kinds of processor error conditions/exceptions exist?
    
- what is an mmu, what sorts of architectures utilize them, why/why not