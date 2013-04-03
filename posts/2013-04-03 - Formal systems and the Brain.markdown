---
title: Formal systems and the Brain
---

This post is guided by Ernesto (neto) and commented or questioned by Carlos (kmels)

# Motivating

_neto:_ It seems rather unrealistic to believe that a formal system can exceed the capacity of human brain. It is simply unbearable to believe that given a set of axioms and rules the system could evolve to equal or exceed human intelligence. 

_kmels:_ Well, we can say that now. By the beginning of the century Russell and his school were very much for the cause of formalizing mathematics with logic alone.

_neto:_ For starters, these formal systems are a human creation, aren’t they..? 

_kmels:_ Yes they are based on what we perceive :) 

_neto:_ This is rather a philosophical question since it can be equally said that they already existed in nature and humanity is just re-discovering them. Nevertheless, the fact is that there exist formal systems that can exceed the capacity of a human brain, even putting together all humanity's brainpower. Some of these systems are not accessible to mankind due to our limited brainpower, but some others are concrete enough to be visualized. 

_kmels:_ What do you mean by not being accessible because of our limited brain power? Are you referring to the existence of systems and our inability to construct them?

_neto:_ The systems exist the problem is that we are not able to define them due to our limited capacity, like the languages that exist but humans nor Turing Machines can recognize

## Formal Systems

_neto:_ To begin the quest to find the limits of human thinking power, lets introduce what formal systems are. A formal system is composed of two parts: the axioms and derivation rules. Axioms are simply pieces of information that are assumed to be `true`. 

_kmels:_ If you have conflicts with these presummptions, you might like to grasp on Kant's metaphysics

_neto:_ Derivation rules are mechanisms that tell us how to discover or create new truths from previous truths inside our formal system. 

_kmels:_ It will be useful for us to define what does it mean for a formal system to be complete. We call a system complete if, and only if, all possible truths are derivable from these derivation rules.

_neto:_ This can be left for another post where we talk about completeness and consistency.. 

_kmels:_ It could, but aren’t we talking about Gödel Incompleteness theorem? We ought to define what completeness is

_neto:_ We could eventually have a post about it, but the theorem requires some background info that we could present in previous posts.  

_kmels:_ All right, so we are not talking Gödel.

_neto:_ Let’s exemplify with some axioms. The following simple example illustrates these concepts:

### Axioms:

 1. $II+I=III$ 
 2. $III+I=IIII$

_kmels:_ How does one read Axiom 1? Two symbols plus one symbol are three symbols? 

_neto:_ That's the interpretation but they are merely characters.

_kmels:_ Ok, but '+' could be a binary operation on elements right?, I just wanted to get my mind clear..

### Productions:

_neto:_ Let $x,y$ and $z$ be any string composed of any number of 1’s. Then if $x+y=z$ is a true, also $x+y_1=z_1$ is true. 

_kmels:_ When you say is true, then you mean that it is an axiom. 

_neto:_ No, because something that followed from any axiom is also true. True means that it is either an axiom or that it was produced by a sequence of rules, i.e. a theorem. 

We can produce more strings with this system using the given axioms and rules:

 4. $II+II=IIII$ (Apply rule 1 to truth 1)
 5. $III+II=IIIII$ (Apply rule 1 to truth 2) **TO-FIX-MAYBE** Al primer termino de 4. namely II (o x segun regla 1) le agregaste un 1 aqui, pero la regla no dice que le podes agregar al primer termino, solo a Y y a Z. O es ‘+’ commutativo??
 6. $III+III=IIIIII$ (Apply rule 1 to truth 5) 

A clever enough reader might have noticed that the given system produces only valid additions. Count all the 1's and check that the equations are always true. In fact, an invalid addition is not possible within this system.  Anyways we must not confuse the meaning we are giving to the system with the system itself. The system is entirely typographical, given a string, it can be replaced by another string according to the rules, that is all the system consists of. 

### Beauty through Lindenmayer

There are other more interesting systems such as the Lindenmayer systems. One of such systems can be defined as follows: 

_kmels:_ Before mentioning new systems, can we say what the relationship is between the last system and the new one? Do they have the same essence?

Axioms:

  L~RR~RRR~

Rules:

~ -> ~L~RR~L~ . This rule states that if we have a valid string, we can produce a new valid string by replacing every ~ with  ~L~RR~L~ 
(to be done)

Now if we apply the only derivation rule for a while and plot results we get the following:

2. L~L~RR~L~RR~L~RR~L~RRR~L~RR~L~
3. L~L~RR~L~L~L~RR~L~RR~L~RR~L~L~L~RR~L~RR~L~RR~L~L~L~RR~L~RR~L~RR~L ~L~L~RR~L~RRR~L~RR~L~L~L~RR~L~RR~L~RR~L~L~L~RR~L~ 

The system can be interpreted as follows:

If we see L, turn 30 degrees left (counterclockwise).
If we see R, turn 30 degrees right (clockwise).
If we see ~ draw a straight line of a fixed size.

If we draw the first three strings we get the following pictures 

And if we keep going...

_kmels:_ OMG! :) How did you do those graphics? 

_neto:_ In Haskell, naturally! 

In fact, this system can be run to infinity to produce a snowflake. 

_kmels:_ We could interpret the infinite application of our rule to be correspondent to a fractal, don’t you agree? 

_neto:_ Yes. Once again, remember that the meaning given to the system (namely the rules used to draw it) are not part of the system. The system is entirely typographical.

### Peano

Now consider this one last formal system, the natural numbers:

(peano axioms)

This system produces the natural numbers. But as should be recalled, the system is entirely typographical, there is no black magic in the system.


## Cantor and Formal Systems 

It is still not convincing to believe that such a simple set of axioms and rules that can be mechanically operated can exceed human capacity. There is in fact a lot of objection to this statement and that's why we introduce Cantor into the game. Cantor was one of the first mathematicians to explore infinity. In fact his ideas were so controversial that even the church had objections against him since he was essentially quantifying God, I mean infinity. Nevertheless, he had something meaningful to say about the good old formal system of real numbers. The definition of this system is very involved and goes beyond the scope of this post but ordinary intuition is enough to continue. For simplicity, consider all the real numbers between 0 and 1. With simple mathematical transformations, every real number can be expressed in terms of 0's and 1's. Now suppose we had a list of all the numbers between 0 and 1:

0.01010110101101010101...
0.01010110110101110101...
0.01011011010011001100...
.

From this we can construct a new number simply by following the diagonal shown above the following way. If we see a 0, write a one and move to the next number, if you see a 1, write a 0 and move to the next number. The new number that is produced has at least one digit different from all the numbers already in the list since each digit is replaced by the opposite digit. If we add this new number to the list, we can then do the same process again and produce a new number. Even if we do this an infinite amount of times it will still be possible to produce a new number.

Does this means we cannot produce all the real numbers between 0 and 1? Yes! Even if we had infinite amount of time we wouldn't be capable of producing all the real numbers. This property is called uncountably infinite. This simply implies there exists real numbers that no human will ever be able to access. This is somehow hidden information that only the system knows, not humans. The only things mortals know about these numbers is that they exists, that's it! In fact there are no set of properties humans can use to group or characterize these numbers.


## Conclusion

As you can see, I have proven before your eyes that there exists a formal system that can exceed the human capacity in the sense it `knows` facts not accessible to humans. This system is different from the natural numbers since given infinite amount of time, any human could enumerate all natural numbers that exist. The property of being uncountably infinite has very strong implications over various fields. There are languages we cannot recognize, there are functions we cannot compute and there are formal systems we cannot use. It will be presented in subsequent chapters how to characterize some of the functions we cannot compute or formal systems we cannot use. Until next time! 
