---
layout: post
title:  "Teaching C++ in SageMathCloud"
date:   2016-12-14 10:38:20 -0700
category: teaching
tags: smc cpp
---

# Teaching C++ in SageMathCloud

Here I summarize some issues specific to using SMC to teach a programming class.
I spend some time at the beginning talking about other things that worked less
well. If you'd rather skip ahead to the results of my SMC experience,
[feel free](#experience).

## Less good options

I have taught introductory computer science with C++ a handful of times. The
course is becoming more popular due to increased interest in a few majors and
minors that require it at the College of Idaho. Anyone who has taught a course
like this knows that the grading is very time-consuming, partly because of the
additional chores of digital file management. The first time I taught this
course was in Spring 2012. The file management scheme I devised used
networked drives that all students and faculty at the College could access. It
was cumbersome for everyone to use, failures and inconveniences were frequent,
and it was probably only a marginal improvement over having the students email
me all their programs.

In Spring 2015, I used an LMS to help me manage the files. After a few years of
Moodle, which I never really used, we switched to Canvas sometime around 2014. I
wanted to be a resource to colleagues who really wanted to do a lot with Canvas,
so I made it my business to learn everything I could about it. It was a huge
improvement over the networked drives. Canvas allows the instructor to configure
assignments so that students upload a file. At the time, C++ source and other
text files did not preview inside Canvas, but now they do. You can also download
all submissions in a `.zip`, edit them to comment and grade, and reupload them
(again as a `.zip`, and with the same filenames), and students can see the
changes you have made to their files. This was a great benefit, saving me hours
of time over the course of the semester in terms of downloading, uploading, and
otherwise managing hundreds of source code files the students submitted.

However, this change did nothing to remedy another headache for the computer
science instructor: the majority of the students' and all of the college's
computers run Windows, not an ideal C++ development environment for the
beginner. (I avoid the use of IDEs in the introductory course, preferring a text
editor and command-line interface.) So in Spring 2015 and again in Spring 2016 I
showed the Windows users how to install MinGW and Sublime Text and babysat their
installations for them. This meant 30 different environments on different
versions of different operating systems; some 32-bit and some 64-bit; some low-
memory, some high; different compilers (some `gcc` and some `clang`) and some
users who took care of their machines and some who didn't.

The next spring I taught the course again, using Canvas in much the same way,
and began to feel more keenly my dislike for the system. At an AIM workshop for
[MathBook XML](http://mathbook.pugetsound.edu/) in April 2016, I had the chance
to use SageMathCloud in a development frame of mind rather than a calculus frame
of mind. Later that summer I read some of Rob Beezer's posts about teaching
group theory and other mathematics courses in SageMathCloud, and I decided to
give it a try with the CS1 course. I had previously thought about using virtual
machines running Linux to alleviate some of the headaches described above, but
was worried that not all students' hardware would be adequate to run a VM with
Ubuntu. (A colleague has had good results with Lubuntu.) I realized that using
SMC would give all the students a standardized, easily controllable development
environment. As a bonus, the code editor would support some Sublime Text
keyboard shortcuts. This is important to me because the shortcuts help a great
deal with indentation. Students are famously indifferent to proper formatting
and the shortcuts make it less tedious to pay attention to it.

## SageMathCloud is the way and the truth

<a name="experience"></a>

I've just wrapped up my first semester teaching C++ in SMC and am pretty
pleased with the results. I used both inline comments (i.e., C++ comments
inserted directly in student code) and the chat interface to comment on
students' code at different times. I used both CSV and Python grading objects,
and made use of the ability to have arbitrary text strings as grades (not just
numeric values). I used SMC in combination with `git`, publishing assignment
directions, associated source and binary files, and reading material to [a
public repo on GitHub](https://github.com/daverosoff/c150-sage). I'll
summarize what I learned below---with the programming aspect of the course in
mind. Rob Beezer and others have written much about how to use SMC to help you
administrate a math course elsewhere.

1. Use chat to ask and answer questions, comment on code, grade, or even hold
   office hours. Especially in the beginning, the chat interface was very useful
   for commenting since I have found that beginners often don't see comments
   left inline by the instructor. Next semester I plan to do even more chatting
   in SMC before assignments are due, which (I hope) will cut down on time spent
   grading and improve retention from one assignment to the next.
2. Teach students to use the terminal. I showed mine how to move and copy files,
   create bash aliases (to use helpful `gcc` flags by default, e.g.), the basics
   of I/O redirection, and the very helpful `open` command.
4. I decided to tell the students about the course GitHub site because it
   seemed like a good idea for them to have access to a "clean" copy of each
   assignment's instructions. Also, I imagined they would want to switch back
   and forth between their code and the assignment, which isn't easy if both
   are in open SMC files. I personally would prefer to be able to Alt-Tab
   between the browser windows (or switch between tabs, again using the
   keyboard). AFAIK it's not possible to switch SMC tabs using the keyboard.
   Most of the students did prefer to visit the assignments on GitHub, with
   their SMC editor open in a second browser window.
5. If you make your assignments public, be sure you don't have any stray
   solutions floating around. I got myself in trouble a few times through being
   careless with `git` and uploaded solutions to the public repo. A separate,
   private repo is a better plan for solutions.

I hope you decide to use SageMathCloud for your next computer science or
programming class!
