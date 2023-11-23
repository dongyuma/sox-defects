# Vulnerability Description
Undefined behavior issues caused by the misuse of keywords were discovered in RTEMS, which will cause the program to run incorrectly and even crash.

# RTEMS download address
https://github.com/RTEMS/rtems

# Vulnerability Details
## An undefined behavior issue caused by the misuse of const keyword was discovered in RTEMS in functon rtems_bsdnet_show_mbuf_stats() of /RTEMS/4.11.3/kernel/rtems/cpukit/libnetworking/rtems/rtems_showmbuf.c file in line 41.
In MISRA C:2012 Guidelines for the use of the C language in critical systems ,there is a rule called "A string literal shall not be assigned to an object unless the object’s type is “pointer to const-qualified char".
Any attempt to modify a string literal results in undefined behaviour. For example, some implementations store string literals in read-only memory in which case an attempt to modify the string literal will fail and may also result in an exception or crash.
This rule, when applied in conjunction with others, prevents a string literal from being modified.It is explicitly unspecified in C99 whether string literals that share a common ending are stored in distinct memory locations. Therefore, even if an attempt to modify a string literal appears to succeed, it is possible that another string literal might be inadvertently altered, which will cause the program to run incorrectly and even crash.
Application standards: C90, C99
![image](https://github.com/dongyuma/sox-defects/assets/87286944/f20dfabd-081c-45b7-8de5-fa059a8132fa)


## An undefined behavior issue caused by the misuse of const keyword was discovered in RTEMS in functon compress2() of /RTEMS/4.11.3/kernel/rtems/cpukit/zlib/compress.c file in line 30.
In MISRA C:2012 Guidelines for the use of the C language in critical systems ,there is a rule called "A cast shall not remove any const or volatile qualification from the type pointed to by a pointer".
Any attempt to remove the qualification associated with the addressed type by using casting is aviolation of the principle of type qualification.
If you attempt to remove const or volatile qualifiers from a type using a cast, it can lead to undefined behavior. Undefined behavior means that the behavior of your program is not defined by the language standard, and it can result in unpredictable and potentially incorrect program execution, which will cause the program to run incorrectly and even crash.

Some of the problems that might arise if a qualifier is removed from the addressed object are:
1.Removing a const qualifier might circumvent the read-only status of an object and result in itbeing modified;
2.Removing a const qualifier might result in an exception when the object is accessed;
Application standards: C90, C99
![image](https://github.com/dongyuma/sox-defects/assets/87286944/65760910-7ca4-4143-8193-a2c3fbc00217)







    
