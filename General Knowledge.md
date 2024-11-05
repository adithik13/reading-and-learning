1. how is static keyword different in C++ vs C? 
2. what is the difference in passing something by reference and passing something by a pointer? 
3. how is const used differently in C++ vs C? 
4. what is an example of the virtual keyword
	1. write some simple classes like Shape, Square, Circle, etc
5. microcontroller specifics:
	1. internals
	2. ISR
	3. pipelines
	4. peripherals
6. RTOS specific questions
	1. mutex vs semaphore
	2. scheduling policies
	3. context switches
7. Linux questions
	1. ssh 
	2. vim 
	3. bash/python
	4. git 
	5. gcc
	6. man pages?
8. systems knowledge: 
	1. read()
	2. write()
	3. poll()
	4. sockets
	5. fork()
	6. system calls
	7. device drivers
	8. device drivers
9. what is RAII?
	1. what is a constructor/destructor
	2. when to call const/ destructor
10. const
11. static
12. public/private
13. what is an int? how many bytes? does it always have the same number of bytes? 
14. what are macros?
15. what is the mutable keyword?
16. what does the C keyword volatile do?
17. what does const do?
18. when does it make sense to use a volatile const variable?
19. is ++i or i++ faster?
20. what is RTOS priority inversion and one way to resolve it?
21. ADC/DAC SPI or I2C
22. what is voltage to turn ratio
23. bitwise operations 
	1. mask on
	2. mask off 
	3. shifts
	4. etc
24. embedded linux misc
25. APQP product dev cycle
26. ‘Making Embedded Systems: Design Patterns for Great Software’
27. [https://rmbconsulting.us/publications/a-c-test-the-0x10-best-questions-for-would-be-embedded-programmers/](https://rmbconsulting.us/publications/a-c-test-the-0x10-best-questions-for-would-be-embedded-programmers/)
28. common chip to chip communication protocols
29. what chips are you familiar with?
30. what framework, HALs, or SDKs have you used?
31. sorting questions
32. what is DMA, when to use it
33. what is a vector interrupt controller
34. have you used RTOS? Which?
35. when to use RTOS
36. mutex and semaphore questions
37. have you used embedded linux?
38. There are very limited interview resources for embedded systems. This statement becomes evident when you compare the Glassdoor interview experiences for job profiles like Software Engineer or even Data Scientist with Embedded System Engineer. Due to this, many candidates go unprepared for the interviews, so the success rate is low. My job allows me to interact with Embedded hiring managers from big tech companies such as Apple, Google, Amazon etc. and gather the information that can help candidates better help with their interviews. Following are some of the top interview questions on key topics of embedded systems that are very popular and often asked in interviews of these MAANG+ companies.  
**System Design**  
- Design a vending machine  
- Design Oculus game controller  
- Design VR glass  
- Design apple pencil  
- Design Audio Mixer (Asked at Facebook Reality Lab)  
- Design a microkernel-based system which can load a file and start execution. (Asked at Facebook Reality Labs)  
- Design Telemetry Service (Asked at Facebook for Embedded Software Engineering role)  
- Design a protocol to send data from the host to the device x bytes at a time. (Asked at Facebook)  
- Design a throwable Panoramic Ball Camera that Shoots 360-Degree Photos.  
- Design a smart garden watering system with multiple zones. Optimize for performance and cost. Would you use a cloud-connected system?  
- Design a Traffic Light Controller.  
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
If you’re unsure about how to start your prep for your next Embedded Software Engineering, let Interview Kickstart be your guide. As pioneers in the [field of technical interview prep](https://www.interviewkickstart.com/courses/embedded-software-engineering-interview-masterclass/?utm_source=Reddit_PM&utm_medium=O9&utm_campaign=post&utm_term=embedded_interview_questions&utm_content=), we have trained hundreds of experienced engineers to crack the toughest interviews and land jobs at their dream companies, like Google & Apple.


For embedded software positions, interviewers may ask non-software specific questions too: low-level processor questions, hardware questions, analog questions, RF questions, safety questions, host computer questions, or anything related to their business or their products (shows that you read up on their company and products). Some embedded software jobs may require you to do more than "just software". Some of the following doesn't have a right or wrong answer, but instead might be used to probe your experiences.

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



I frequently get asked for advice on getting into embedded internships and entry level, so I decided to put together a simple guide based on my experience. Feel free to add your advice or perspective. Note that this is an embedded _software_ guide. There are many embedded systems jobs out there beyond software; this isn't the only path.

**Disclaimer:** This guide is based on my anecdotal, subjective experience. I'm a primarily self-taught embedded software / firmware engineer, living in the Bay Area, 1.5 YOE, with two embedded systems internships, and 1 full time firmware position, currently looking for my 2nd position, and currently interviewing with the high compensation companies. I decided to make this career change 2 years ago, with no prior software or technical degree or experience. What worked for me, may not work for you. I highly encourage you to continuously refine redirect your path based on your own research through talking with working engineers, looking at job postings, and reading articles.

## Rule # 1: Build and show off skills that are in-demand by employers.

This is the advice I give to anyone looking for a job in any industry.

What are the skills that are in-demand? This is highly dependent on the area you live in, and the industries around you. Go to LinkedIn / Google / Indeed, and look at all the entry level and internship job postings for embedded software / firmware, and tabulate skills that are asked for. This doesn't need to be rigorous, and there will probably be a bunch of terms and concepts that you don't know -- that's okay. For now, just focus on the common concepts.

My list ended up looking something like this:

- C
- C++
- Testing
- RTOS
- Board bring-up
- Driver development
- I2C
- Sensors & Actuators
- ARM
- Linux Kernel Development
- Python
- Microcontrollers
- UART
- Bluetooth / Wifi / IEEE 802.11
- System Debug
- OS Architecture / Design
- ...

One thing to also notice is common clusterings of skills: microcontrollers, embedded linux, hardware testing, networking, automotive, and IoT are the common ones I've seen in my search.

Personally, I focused on the most in-demand, broadest, and fundamental skills first, because I wanted a job, and I wanted the ability to pivot to different types of development if I ended up disliking a subfield.

## Fundamentals

The following topics / courses will give you a strong foundation for embedded systems software development, and questions about the basics will likely come up in interviews:

1. **Introduction to Programming.** [CS50](https://www.edx.org/course/cs50s-introduction-to-computer-science) is a great first course. Covers a lot, but has a ton of auxiliary resources.
2. **Data Structures and Algorithms.** There's tons of resources out there already, so I won't go into that here.
3. **Computer Organization / Systems.** (Learn the basic hardware in a computer, and learn assembly)
4. **Operating Systems.** The combination of a good computer organization and assembly course, with a good operating systems course answered so many questions for me and filled in a ton of blanks.

## How do I build these skills?

1. A computer engineering, electrical engineering, or computer science degree, with a selection of electives focused on embedded software concepts will get you 75% of the way to a job, and will make it significantly easier for you to get interviews.
    
2. [Embedded Systems Rule the World](http://users.ece.utexas.edu/%7Evalvano/Volume1/E-Book/), and [Real-Time Bluetooth Networks - Shape the World](https://www.edx.org/course/real-time-bluetooth-networks-shape-the-world) will get you good enough projects to land a job if you complete them, and if you can intelligently talk about the covered topics. Whether you're self-taught, or getting a degree, I 100% recommend working through these two courses as a first step towards getting employable, real world skills. (If you're completely new to programming, complete CS50 first).
    
3. Learn to Google! There are so many resources out there, at all levels, to help with your learning. Each concept that you need to learn, you need to understand why people use it, alternatives, what problem it solves, and ways to implement it. Find tutorials that work for you -- for some concepts, I've had to go through multiple textbooks and multiple tutorials before they finally clicked. Be a relentless autodidact.
    

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

## Applications

The best way to get your application moved forward is through personal connections, and recommendations. But, sometimes that isn't an option, and you have to cold apply.

My advice is to apply to positions that you meet >=50% of the requirements.

Make sure you get you resume reviewed by professionals in the field before applying.

If you get a low response rate, you need to get your resume re-reviewed, or you need to build better projects that better demonstrate the skills employers are looking for.

## Interview Questions

In addition to typical software interview preparation, embedded software interviews tend to ask some repetitive questions. I don't know how many times I've answered what volatile and static are. Here are some typical questions:

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



Really nice list of questions. Most are great, some feel a little bit outdated or domain specific: 39, 51, 70, 75.

Q78 might be better asked as "how would you manually unroll a loop?" I think many people are aware of the pattern, but don't know how it is called.

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