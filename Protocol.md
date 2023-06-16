# Protocol
A set of rules used to comminicate between parties 

https://github.com/0Domlightning0/TheJournal/blob/main/ProtocolDoc.md#implicit-agreements

## Real life example of I2C
- Uses time inbetween bursts of power using an internal clock 
- Uses mere milliseconds to tell the difference 
- Can run from 100kb/s to 400kb/s
- Programmed protocols remove human error and allow better memory of codes
- Legnth, intensity, power and different methods can be used to convey data
- If you can measure it, it is data you can receive 

## Our protocol 
- Using 3 flags we created a 4 trit system to call upon specific characters to be presetned
- Other trit commands to complete non character commans
- Simplicity = more accuracy / more time. Shown with brute force  
( https://github.com/0Domlightning0/TheJournal/blob/main/ProtocolDoc.md#brute-force )
- Complexity = less accuracy / less time. Shown with alphabet   
- ( https://github.com/0Domlightning0/TheJournal/blob/main/ProtocolDoc.md#brute-force )
- Sending around 2b/s of info

