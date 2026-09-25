# Project Charter — For-Fun Zero Hour Experiment

## Status

**ACTIVE EXPERIMENT, BOUNDED SCOPE**

This is not a new full production project.

## Goal

Produce the smallest playable custom experience that proves we can comfortably author content for Zero Hour using the released source code + WorldBuilder ecosystem.

## Success condition

A local playable build with:

- one custom map;
- one custom faction or micro-faction slice;
- at least one custom unit;
- at least one custom building;
- one changed weapon/ability/economy rule;
- AI opponent or scripted enemy;
- a clean repeatable local launch procedure.

## Non-goals for the first phase

Do **not** start:

- standalone engine conversion;
- renderer rewrite;
- modern matchmaking;
- custom strategic campaign layer;
- procedural map generation;
- mass asset production;
- commercial distribution;
- full faction roster;
- multiplayer service backend.

## Design principle

Keep the original Generals/Zero Hour responsiveness and asymmetry. Change content first, engine architecture later.

## Repository hygiene

- Keep `main` upstream-friendly.
- Experimental work lives on lab branches.
- Never remove upstream copyright/license notices.
- Never commit third-party proprietary SDKs.
- Do not commit personal local filesystem paths.
