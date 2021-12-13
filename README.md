# Practical_Exam_Computer_networks

# Practical 1 (Go Back N Sliding window protocol)
Go back N Protocol-
 

Go back N protocol is an implementation of a sliding window protocol.

The features and working of this protocol are explained in the following points-

 1.In Go back N, sender window size is N and receiver window size is always 1.
 2.Go back N uses cumulative acknowledgements.
 3.Go back N may use independent acknowledgements too.
 4.Go back N does not accept the corrupted frames and silently discards them.
 5.Go back N does not accept out of order frames and silently discards them.
 6.Go back N leads to retransmission of entire window if for any frame, no ACK is received by the sender.
 7.Go back N leads to retransmission of lost frames after expiry of time out timer.
 
 
# Practical 2 (Cyclic Redundancy Check)
Properties Of CRC Generator-
The algebraic polynomial chosen as a CRC generator should have at least the following properties-
Rule-01:
It should not be divisible by x.
This condition guarantees that all the burst errors of length equal to the length of polynomial are detected.
Rule-02:
It should be divisible by x+1.
This condition guarantees that all the burst errors affecting an odd number of bits are detected.
Important Notes-
 
If the CRC generator is chosen according to the above rules, then-

CRC can detect all single-bit errors
CRC can detect all double-bit errors provided the divisor contains at least three logic 1’s.
CRC can detect any odd number of errors provided the divisor is a factor of x+1.
CRC can detect all burst error of length less than the degree of the polynomial.
CRC can detect most of the larger burst errors with a high probability.
 
Steps Involved-
Error detection using CRC technique involves the following steps-
Step-01: Calculation Of CRC At Sender Side-
At sender side,
A string of n 0’s is appended to the data unit to be transmitted.
Here, n is one less than the number of bits in CRC generator.
Binary division is performed of the resultant string with the CRC generator.
After division, the remainder so obtained is called as CRC.
It may be noted that CRC also consists of n bits.
 

Step-02: Appending CRC To Data Unit-
At sender side,
The CRC is obtained after the binary division.
The string of n 0’s appended to the data unit earlier is replaced by the CRC remainder.
 

Step-03: Transmission To Receiver-
The newly formed code word (Original data + CRC) is transmitted to the receiver.
 

Step-04: Checking at Receiver Side-
At receiver side,

The transmitted code word is received.
The received code word is divided with the same CRC generator.
On division, the remainder so obtained is checked.
 

The following two cases are possible-
Case-01: Remainder = 0
If the remainder is zero,
Receiver assumes that no error occurred in the data during the transmission.
Receiver accepts the data.
 
Case-02: Remainder ≠ 0
If the remainder is non-zero,
Receiver assumes that some error occurred in the data during the transmission.
Receiver rejects the data and asks the sender for retransmission.
