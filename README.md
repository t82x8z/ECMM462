java c
ECMM462 – Fundamentals of Security
Academic Year: 2024/25
Title: Continuous Assessment
Submission deadline:  19 November 2024 before 12:00 (Midday)
This assessment contributes 40% of the total module mark and assesses the following intended learning outcomes:
•  Module Specific Skills and  Knowledge.
–  Explain the fundamental information/cyber security concepts
•  Personal and  Key Transferable / Employment Skills and Knowledge
–  Assessing and understanding the limitations of technologyThis is an individual assessment and you are reminded of the University’s Regulations on Collaboration and Plagiarism.  You must avoid plagiarism, collusion and any academic misconduct behaviours.  Further details about Academic Honesty and Plagiarism can be found at https://ele.exeter.ac.uk/course/ view.php?id=1957.
Use of GenAI tools in Continuous Assessment for ECMM462 – Fundamentals of SecurityThe University of Exeter is committed to the ethical and responsible use of Generative AI (GenAI) tools in teaching  and  learning,  in  line  with  our  academic  integrity  policies  where  the  direct  copying  of  AI- generated content is included under plagiarism, misrepresentation and contract cheating under definitions and offences in TQA Manual Chapter 12.3.  To support students in their use of GenAI tools as part of their assessments, we have developed a category tool that enables staff to identify where use of Gen AI is integrated, supported or prohibited in each assessment.  This assessment falls under the category of AI-supported.
You can find further guidance on using GenAI critically, and how to use GenAI to enhance your learning, on Study Zone digital.
When submitting your assessment, you must include the following declaration, ticking all that apply:
AI-supported/AI-integrated use is permitted in this assessment.  I acknowledge the following uses of GenAI tools in this assessment:
•  I  have used GenAI tools for developing ideas.
•  I have used GenAI tools to assist with research or gathering information.
•  I  have used GenAI tools to help me understand key theories and concepts.
•  I have used GenAI tools to identify trends and themes as part of my data analysis.
•  I  have used GenAI tools to suggest a plan or structure for my assessment.
•  I have used GenAI tools to give me feedback on a draft.
•  I have used GenAI tool to generate image, figures or diagrams.
•  I have used GenAI tools to proofread and correct grammar or spelling errors.
•  I have used GenAI tools to generate citations or references.
•  Other:  [please specify]
•  I  have not used any GenAI tools in preparing this assessment.
•  I declare that I have referenced use of GenAI outputs within my assessment in line with the University referencing guidelines.Please note:  Submitting  your work without an accompanying declaration, or one with no ticked boxes, will be considered a declaration that you have not used generative AI in preparing your workIf a declaration sheet cannot be uploaded as part of an assignment  (i.e.   at the start of an essay), students understand that by submitting their assessment that are confirming they have followed the assessment brief and guidelines about GenAI use.

1    Symmetric Encryption                                                  (40 marks)The Feistel structure Figure 1 is a foundation of many modern symmetric block ciphers.  It requires a 2w bit input and splits it into a left (bottom) and right (top) part of w bit each.  It then proceeds in n rounds to produce a 2w bit output.  Each round consists of the following steps:
•  The top w bits are combined with the round key ki  by a round function f.
•  The bottom w bits are combined with the output of f by bit-wise exclusive or (XOR).
•  Then, the top and bottom bits are swapped and passed on to the next round.

Figure 1:  Feistel structure.Task 1                                                                                                      (40 marks)
For this task, you are required to implement a version of the Feistel structure in Python 3 (version 3.9 or above). Only use the packages included in the template file feistel .py provided on the ELE page.
Your  implementation should work on 8  bit  inputs and  use  bitwise  OR as  its  round function.  Your program should be called feistel .py and take the following input parameters:
•  The first parameter is an optional option -d (for decryption).
•  The second parameter is an 8 bit input string.
•  The third parameter is the number of rounds.
•  The next parameters are the different round keys.
The program should return only the 8 bit result. For example,
> pyth on 3   f e i st e l . py    1 0 1 0 1 0 1 0   5    0 1 0 1    1 1 1 1   1 0 1 0   0 1 0 1   0 1 0 1 XXXX XXXX
should encrypt 10101010 in 5 rounds with round keys 0101, 1111, 1010, 0101, and 0101 respectively.



2    Asymmetric Encryption                                                (60 marks)
2.1   Asymmetric Encryption Using Permutation Matrix Lookup
In the following, we describe a simple mechanism for asymmetric encryption.  The idea is to represent 代 写ECMM462 – Fundamentals of Security 2024/25Python
代做程序编程语言encryption and decryption using matrix lookups. To this end, three types of matrices are used:
M1  is just a sequence of N elements and contains a  random permutation of all integers between 1 and N.  For example m1 = (4, 3, 2, 5, 1) could be an example for N = 5.  It is used to construct a public key from a private key.  For example, if we assume that our private key is 2, then the corresponding public key, according to our example matrix m1, is given by m1(2) = 3.
M2  is  an N × N matrix such that each row represents a random permutation of all integers between 1 and N.  For example, for N = 5 we may have:

It  is  used  for  encryption.    For  example,  to encrypt 3  using our  matrix m2 and  key 2, we get m2(2, 3) = 3.M3  is an N × N matrix such that each column represents a random permutation of all integers between 1 and N.  It is used for decryption.
The matrices must be constructed in a way such that for all k and p, with 1 ≤ k, p ≤ N, the following property holds:M3(M2(M1(k), p), k) = p                                                      (1)



Tasks 2.1                                                                                                 (40 marks)T1  Construct an example of M1,  M2, and M3 for N = 5.  Hint:  first, randomly create  M1 and M2 and
then construct M3 such that property Eq. (1) holds. T2  Encrypt the number 4 and then decrypt it again.
T3  Determine if the encryption scheme provides adequate security, and explain why.
T4  Implement  the  key generation scheme  in  Python 3  (version 3.9 or above) using only the following basic libraries:  sys,  re,  and random.  It should be called myPKE and take one input parameter, which represents N.  It should then generate three random matrices m1, m2, and m3, which satisfy Eq. 1.  For example:


> pyth on 3   my PKE   5
m1 :
4 ,3 ,2 ,5 ,1
m2 :3 ,1 ,2 ,5 ,41 ,4 ,3 ,2 ,54 ,5 ,2 ,3 ,13 ,2 ,1 ,4 ,52 ,3 ,5 ,1 ,4m3 :
. . . . . . . .
. . . . . . . .
. . . . . . . .
. . . . . . . .
. . . . . . . .
2.2    Prime-Based Asymmetric Encryption
Consider the following scheme by which B encrypts a message for A.
1.  A chooses two large primes, P and Q, such that:
•  P is relatively prime to Q−1
•  Q is relatively prime to P −1
2.  A publishes N = PQ as their public key.
3.  A calculates P,  and Q, , such that:
•  PP,  = 1 (mod Q−1)
•  QQ,  = 1 (mod P - 1)
4.  B encrypts message M as C = MN   (mod N).
5.  A finds M by solving:
•  M = CP,    (mod Q)
•  and M = CQ,    (mod P)Task 2.2                                                                                                  (20 marks)
For this, you should first encrypt the number 5 555 555 and then decrypt the number 5 555 555 using the above scheme.
T1  Choose prime numbers between 5,000 and  10,000.
T2  List every intermediate step for encryption and decryption.
Hint
You may use the following to help you with your answer:
•  Chinese remainder theorem
•  Fermat’s little theorem
•  Chinese  Remainder Calculator: https://www.dcode.fr/chinese-remainder
•  Modular exponentiation: https://www.dcode.fr/modular-exponentiation.
•  Coprime checker: https://www.dcode.fr/coprimes.
Marking criteria
•  Task1:  You will  receive a maximum of 25 marks for correctly implementing encryption if all test cases pass and an additional 15 marks for correctly implementing decryption if all test cases pass. Partial marks will be awarded if your implementation successfully encrypts or decrypts some of the test cases.
•  Task2.1:
–  T1 Matrices Construction:  Full marks are awarded for correctly constructing examples of M1, M2, and M3 such that property Eq.  (1) holds.
–  T2 Encryption and Decryption:  Full marks are awarded for successful encryption and decryption that correctly returns the original number.  Partial marks may be awarded if either encryption or decryption works partially.
–  T3  Security  Scheme Assessment:  Full  marks  are awarded for a well-explained and justified assessment of the scheme’s security.
–  T4 Implementation:  Full marks are awarded for implementing the function myPKE that correctly generates three random matrices, m1, m2, and m3, satisfying Eq.  1.  Partial marks are granted if the implementation meets some but not all of the required conditions or if the implementation is generally correct but contains minor errors.
•  Task2.2:
–  Prime  Number  Selection:   Correctly  choose  two  prime  numbers  that  meet  the  specified conditions.  Partial marks will be awarded if the primes fall within the range but do not fully meet the criteria.
–  Listing  Intermediate Steps:  Clearly  listing and explaining every intermediate step for both encryption and decryption.  Full marks will be awarded if all steps are documented accurately; partial marks will be given if steps are missing or unclear.
•  Note:  Before submitting your coursework,  please ensure that the  implementation com- piles and returns output successfully using Python 3.9 or above.  Implementations that fail to run or do not provide an output will receive zero marks.

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
