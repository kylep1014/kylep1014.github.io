---
title: "Voir Dire as a Game: The Strategy of Jury Selection"
date: 2026-11-12 12:00:00 -06:00
tags: [game theory, law, research]
description: A game-theoretic model of peremptory strikes in jury selection, written for my graduate Game Theory course (MATH 460) at Loyola.
---

For my graduate Game Theory course (MATH 460) at Loyola, I'm writing a paper that treats jury selection as a strategic game between the prosecution and the defense.

## The question

During voir dire, each side can remove a limited number of prospective jurors with **peremptory strikes**, without giving a reason. In federal court, each side gets three strikes in a misdemeanor case. In a felony case, the prosecution gets six and the defense gets ten.

Strikes are scarce, so using them is a strategic problem. A strike spent on a mildly unfavorable juror can't be used on a worse one later, and the other side is making the same calculation with the opposite goal. So when should each side strike?

## The model

I model voir dire as a two-player, zero-sum game:

- Prospective jurors arrive one at a time, each with a "sentiment" between 0 and 1 measuring how inclined they are to convict.
- The prosecution, then the defense, decides whether to strike each juror before the next one appears.
- Once the jury is full, the prosecution wins if the jury's average sentiment is above one half.

From this setup I derive a recursion for each side's probability of winning and prove that the two sides **never want to strike the same juror**. That means optimal play reduces to simple threshold strategies: the prosecution strikes anyone below one cutoff, the defense strikes anyone above another, and everyone in between is seated.

## What the model shows

- **With twelve seats, strikes go only to the extremes.** In a federal misdemeanor trial, the prosecution should strike the first juror only if their sentiment is below about 0.19, and the defense only if it is above about 0.81. Since each juror is a small part of the verdict, strikes are saved for extreme jurors.
- **Strike allocations matter a great deal.** Equal strikes leave the game even, but the federal felony allocation of six strikes to ten gives the prosecution only about a **19%** chance of winning in the model.
- **Peremptory strikes push juries toward the middle.** More seats and more strikes both mean that only the most extreme jurors are removed.

## Beyond averages: who persuades whom

Real juries deliberate, so a juror's value depends on influence as well as opinion. Using DeGroot's model of how groups reach consensus, I show that the "average sentiment" rule is exactly the case where every juror trusts every other juror equally. I then sketch an extension in which each juror also has a persuasiveness score. In a worked example, striking a moderately unfavorable but highly influential juror helps the prosecution more than striking the most extreme one.

The model also shows why a single stubborn holdout can lead to a hung jury, which favors the defense under a unanimity rule.

## Building on prior work

The paper builds on earlier game-theoretic studies of jury selection by Roth, Kadane and DeGroot (1977), Brams and Davis (1978), and Alpern, Gal and Solan (2010). It sets aside the legal limits on peremptory strikes, such as *Batson v. Kentucky* (race) and *J.E.B. v. Alabama* (sex), to focus on strategy.
