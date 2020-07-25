# gf-pawncc-ctr
The Pawn Language compiler with tweaks to support Game Freak's AMX fork in the Gen 6/7 Pokémon games.

# What is this?

The Pawn Language is an embedded scripting language derived from Small-C and currently maintained by ITB CompuPhase at [https://github.com/compuphase/pawn/](https://github.com/compuphase/pawn/).

The Pawn Compiler is a program that converts - compiles - said language's source files into executables for the Pawn Abstract machine (.amx files).

When Game Freak elected to implement the Pawn abstract machine into their Pokémon games, they were likely discontent with the openness of it and decided to store function names as hashes.
This version of the Pawn Compiler has been modified to:

1. Store all public function/variable names as hashes.
2. Use the maximum level of optimization by default.
3. Use 63 as the maximum symbol name length (instead of the 31 default of Pawn).

# Why is this?

Let me tell you a story that also begins with stardust...

`GAME FREAK CO. LTD. HEADQUARTERS`

`CARROT TOWER 22F, TOKYO, JAPAN`

`CIRCA 2012`

**Field development lead**: Alright, listen up. There is a high priority request from our level design team for the new Pokémon game. Apparently, they aren't very fond of our ages-old scripting language and are urging us to implement something more high level.

**Field developer 1**: Bruh, you mean we have to design a new scripting language from the ground up? Again? Bear in mind, we are Game Freak, not some coding wizards.

**FDL**: Yup, and you aren't getting any ice cream in the canteen till you do.

**FD2**: You serious?

**FDL**: Lmao of course not. You task for today is to find some obscure open-source game scripting project without much licensing hassle and try to implement it within our engine, hopefully without breaking it like back in '96.

**FD1**: Yeah I actually know one right off the bat, but I call dibs on all our ice cream if we choose to go for it.

**FDL**: Even better! Go ahead then

**FD1**: Well, since GTA V is coming out some time next year, I decided to play some San Andreas during lunch break and apparently there's a small but powerful scripting engine forked from some obscure 1980s C wannabe in the multiplayer mod...

**FD3**: Shhh, dude. If the Nintendo execs heard you saying the M-word, chances are Miyamoto is already on his way with the vaporizer.

**FD1**: Oh frick, not the vaporizer!

**FDL**: Hey, people, back to the topic. How about we take a look at that scripting engine then?

`A FEW DAYS LATER`

**FDL**: So I got some feedback from the higher-ups about our Pawn implementation. Looks like it can get a green-light, but only as long as we make sure to expunge the M-word-ing possibilities the language provides.

**FD1**: Meaning... what?

**FDL**: Well, since we are calling in-engine functions from the abstract machine, we need to obfuscate them somehow.

**FD2**: That's easy, right? Just name them a/1/2/3 et cetera.

**FDL**: And have our inbox full of level designer complaints? Hell no.

**FD2**: How about compile-time obfuscations then? Store the function names as hashes or something. Way harder to make sense of.

**FD3**: Ohno. Ohnononononono. Does that mean I have to write C? I was hoping never to see that again when we finally switched to C++ with the CTR.

**FDL**: Whoever does it gets all of today's ice cream.

**FD1**: Damn, that's all you had to say boss.

**FD2**: Yeah, cool, but... if we make modifications... that means we have to submit to Section 4 of Pawn's Apache License.

**FDL**: Lol tf is a license?

**FD3**: It came with your damn XBOX.

**FD1**: Meaning exactly... what?

**FD2**: Well the Pawn language has a license exemption to allow us to link the Pawn libraries without the obligations of shipping a copyright notice and stuff like that with out program.

**FD1**: Ooh, yeah, I remember skimming over something like that. Applies if we distribute the "Work" in Object form, right? So what's the problem?

**FD3**: Found it. Says right here: "This exception applies only to redistributions in "Object" form (not "Source" form) and only if no modifications have been made to the "Work"."

**FDL**: Hey. Chill. Noone has to know, right? We don't have to tell anyone. The M-worders will take years to figure out it's even Pawn anyway.

**FD1**: LGTM. Imma write the obfuscator, so get the ice cream ready.

**FD3**: I thought you were getting vaporized?

**FDL**: Heeey, let's not worry about that. We did a good job today. Who's up for some SA-MP?
