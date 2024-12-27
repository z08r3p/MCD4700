java c
MCD4700 Introduction to Computer Systems,   Networks   and   Security   - T2 2024
Assignment 2 –   Processes and   MARIE   Programming_InstructionPurposeProcesses and programs   are what makes computers   do what   we    want them to do.   In the first   part of this assignment, students will   investigate the processes running on their   computers.   The   second   part   is about   programming   in   MARIE assembly language. This willallow students to demonstrate their comprehension of the   fundamental way a processor works.The assignment relates to   Unit Learning   Outcomes 2,   3   and   4.Your   taskFor part   1, you will write a short   report describing   the   processes that   are running on   your   computer.For part 2, you will   implement a simple game   in   the   MARIE   assembly   language.Value20% of your total marks for the   unitThe assignment is   marked out   of   100   marks.   Word   LimitSee   individual   instructions   Due   Date   11:55   pm   Friday 9 August 2024 (Week7)Submission●       Via   Moodle Assignment Submission.●       Turnitin will be   used for similarity   checking   of all submissions.●       This   is an   individual assignment   (group work   is   not permitted).●       Handwritten work   is   not accepted.   docx for the written tasks.●         MARIE files for the second   part●         DRAFT submission   is   not assessed.●       You will   need to explain your   code   in   an   interview.
1.   Processes (15   marks)
Calculate the turnaround time for the following   processes and subsequently calculate their   average turnaround timeProcessProcessing TimeP16P25P33P42P57P64P71
a-       In   FCFS first-come first-servedProcessProcessing Timeturnaround time         
b-       In SJF shortest   job firstProcessProcessing Timeturnaround time         
c-       In   Round   Robin with slice   time=3ProcessProcessing Timeturnaround time         

2. MARIE (65   marks)In this   task   you   will develop a MARIE application that performs some manipulation of   characters,   strings   and   numbers. We will   break   it   down   into small   steps for you.   Most   of   the   tasks   require   you to write code and test cases. The code must contain proper comments and well indented.   You submit it as .mas files together with the rest of   your assignment. The test cases should also   be working, self-contained   MARIE assembly files (without requiring much   input from   the   user).In-Class   interviews:   You   will   be   required   to   demonstrate   your   code   to   your   tutor   after   the   submission   deadline.   Failure   to   demonstrate   will   lead   to   “zero   marks”   being   awarded   to   the   entire   programming part of this assignment.
Background -   Lists   of dataThis   section   introduces   the   concepts   you   need   for   the   rest   of   the   assignment.   A   string   is   a   sequence   of   characters.   It’s   the   basic   data   structure   for   storing   text   in   a   computer.   There   are   several different   ways of representing a string in memory and how   to deal   with strings of   arbitrary   length.
For this assignment, we will use the following string   representation:
●         A string is represented in contiguous memory locations, with each address containing one   character.
●         The characters are encoded using   the ASCII   encoding.
●          End of a string   is marked by the ASCII   character ‘   .   ’ (i.e.   dot   or full-stop).
●         A string   can   be of any arbitrary   length,   and will   be   terminated   by   a   ’.’,   and   it   may   contain   any   of   the   following:   alphabets   (A-Z,   a-z),   numbers   (0-9),   ASCII   Space   Character   (Hex
020) and   New   Line   (Hex 00A).
Here    is    an    example.    A    string    “Dong    Satria.”          will    be      represented      in      memory      (written    as hexadecimal numbers):04406F06E06702005306107407206906102EDong   Satria.Note that, in the above example,   for a string   with 10 characters,   we need (10+2)   words of MARIE   memory   in order to store all the   characters   belonging   to   that   string   (including   a   space   and   a ‘   .   ’   characters).
In   MARIE assembly language   programming, we can make use   of the ADR   command, the   HEX   keyword and a   label “myString” to put this   string   into   memory:
myStringAddr,         ADR      myString
myString,                  HEX   044            /’D’
HEX   06F          /’o’
HEX   06E          /’n’
HEX   067          /’g’
HEX   020            /Space
HEX   053          /’S’
HEX   061            /’a’
HEX   074            /’t’
HEX   072            /’r’
HEX   069            /’i’
HEX   061            /’a’
HEX   02E            /’   .   ’
2.1.            Your name as a   MARIE   string    (5 marks)The   following   example   of   a   MARIE   string   “myString”   encodes   a   name   and   an   ID   using   ASCII   characters. The “name”   is separated from the   ID by   an ASCII   character   “Hex   00A”   (New   Line).   Different parts of a name are separated by another ASCII character “Hex 020” (Space). And the   entire string, consisting of a name and   an   ID,   is terminated   by   a   dot   ‘   .   ’ character.
Please代 写MCD4700 Introduction to Computer Systems, Networks and Security – T2 2024 Assignment 2Python
代做程序编程语言 see the example below. The label “myStringAddr” holds the address of   the   first character of the string. You   need to follow this   MARIE string while solving the task given   below.
myStringAddr,
ADR
myString
myString,HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX   HEX
044          /’D’
06F          /’o’
06E          /’n’
067          /’g’
020            /Space
053          /’S’
061            /’a’
074            /’t’
072            /’r’
069            /’i’
061            /’a’00A            /NL(New Line)
032          /’2’
031          /’1’
038          /’8’
033          /’3’
039          /’9’
039          /’9’
030          /’0’
030          /’0’
02E            /’   .   ’Prepare   a   MARIE   program to encode a string   that   includes   your full   name   (first   name   and   last   name) and your student   ID using ASCII characters.   Following the   above   example, you   need   to   use two   labels, one   label (e.g. “myString”) to   store   the   first   character   of the   string,   and   another   label (e.g. “myStringAddr”) to store the address of the first   character of the same   string.You   need   to   submit   a   MARIE   file   that   contains   codes,   using   the   ADR   command   and   HEX   keywords   (like   the   above   example),   so   that   after   assembling,   your   name,   ID   and the   address   (of   the   first character of   the string) is stored in MARIE memory. The codes must be accompanied   by   appropriate   comments   (as   a   paragraph   before   any   block   of code   or subroutine   or   as   inline   comments   wherever   appropriate).
2.2.             Printing string    (10 marks)Prepare a   MARIE   program that can   print the ASCII ‘   .   ’ terminated   string   of your   name   and your student   ID that you have implemented in task 2.1. You   may   use the “Output”   instruction to   print   characters   in   the   MARIE   output   space.   The   program   should   be   able   to   print   any   string   that   terminated with ‘   .   ’.Hint:   In   your   program,   you   need   to   use   a   label   “myString”   that   holds   the   start   address   of the   string   (like,   myStringAddr)   that   you   want   to   print.   Then,   you   should   load   a   character from   the   address “myString”   , print the character, then increment the address by one, and keep doing that   up   to   the   character   loaded   from   the   address   is   a ‘   .   ’   (which   signals   the   end   of the   string).   The   output   may   look   similar to   the   output   below.   The   codes   must   be   accompanied   by   appropriate   comments   (as   a   paragraph   before   any   block   of   code   or   subroutine   or   as   inline   comments   wherever   appropriate).
Inside the   MemoryDong   Satria21839900
Figure   1:   Print your name   and   ID
2.3 Subroutine to print the name and the colour   of   a   suit   (25 marks)
The standard 52-card deck of French-suited playing cards is widely utilised in various card   games. This deck consists of 13 ranks in each of   the   four suits: clubs (♣), diamonds (◆),
hearts (♥), and spades   (♠).
Your task is to prepare a MARIE subroutine named subSuit, designed to accept one of   four   characters (c, d, h and s) representing the suits of   the cards.   Subsequently, based   on   the
input character, the subroutine should display the name and the   colour   of   the   corresponding   suit.
You are required to provide the   following messages associated   with the input:
Input (Decimal)
Output (Unicode)c
Black   Clubsd
Red Diamondsh
Red Heartss
Black Spades
Anything else
Wrong Suits
Write a main program where the user   will be:
a.    Asked to enter (input) a character.
b.      Find and display (output) the appropriate message.The   code   should be   well-commented   to   explain its   functionality.   To   ensure   clarity   and   efficiency,   the   code   should   be   structured   as   a   subroutine   called   using   the   JnS   instruction   in   MARIE   assembly    language.    Additionally,    the      code      should      avoid      duplication      and      unnecessary   statements.
Figure 2.a: Reading a Character and Display a Message
Figure 2.b:   Reading Wrong Character
2.4 Assembly   Language and   Machine   Language    (15 marks)
This   task is for HD students
To get   HD   in this assignment you   have to think again   before ignoring   this   task
a.      Write at least four differences   between (at   most   200 words):   
i.               Assembly   Language
ii.                Machine   Language
b.       Prepare a MARIE   program that   prints the digits   from   9   to   1   followed   by   a   plus   (+)   sign   in:
i.               Assembly   Language
ii.                Machine   LanguageThe codes must   be accompanied   by appropriate comments   (as a   paragraph   before   any   block      of code or subroutine or as inline comments wherever   appropriate).   The   code   of the assemble   and the machine should be   in one   MARIE file called   (AssemblyANDMachine).



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
