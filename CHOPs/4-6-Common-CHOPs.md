\#\#\# \*4.6 Common Beginner Operators\*

This section is an introduction to some of the channel operators that are used in many situations. There is an example file that is included in the .zip folder.

\#\#\#\# Generator CHOPs

\#\#\#\#\# Constant

The \`Constant\` operator holds up to 40 unique constant values. The channel name is defined in text field on the left, and the value is defined with the number field / slider on the right.

When a Constant CHOP is created, only 1 channel is active. If a channel is not active, it's number field is greyed out.

To activate a channel just give it a name, and the number field will light up as well as show up in the operator viewer.

To create multiple channels with the same value, you can name the channels using pattern matching.

If you enter \`chan\[1-4\]\` in the name field, 4 channels will be created: \`chan1\`, \`chan2\`, \`chan3\`, and \`chan4\`. These channels will all have the same value.

!\[Constant\]\(../img/constant.jpg\)

\#\#\#\#\# Noise

This CHOP generates a set of pseudo-random points according to the settings in the operators Parameters. There are 6 different algorithms to choose from, each with different characteristics and may suit some situations better than the others.

The basis for each algorithm is the \`seed\` value. You can have 2 Noise CHOPs with the same values, and the noise would look the same, but if you change the seed, it will generate a set of points based on the new seed number, creating a different result.

To create movement, you can change values on the \`Transform\` page. If you enter \`absTime.frame\` to the first \`Translate\` field, you can see that the noise begins to scroll along the x-axis.

To create multiple channels of noise, go to the \`Channel\` page of the Parameters, and in the \`Channel Names\` field, enter the names of the channels separated by a space.

The number of samples you would like to generate is determined by the settings on the \`Channel\` page, with the \`Start\`, \`End\`, and \`Sample Rate\`. The amount of time multiplied by the sample rate. But if you only need 1 sample at a time, you can go to the \`Common\` page, and turn the \`Time Slice\` toggle to \`On\`. This creates 1 random value per channel for each frame, which requires less CPU usage.

\#\#\#\#\# Pattern

The Pattern CHOP generates a function that is a set amount, or array, of samples.

The size of the array is set by \`Length\` on the \`Pattern\` parameter page and the type of function is chosen by \`Type\`.

\`Cycles\` is the amount of times the function loops within the amount of samples.

There are settings to control your pattern, depending on what \`Type\` you have chosen.

\`Taper\` has a beginning value and an end value, and taper, or expands, depending on which one is higher.

\`From Range\` and \`To Range\` are very useful for something like a sine wave that creates a \`-1\` to \`1\` value, but you need a \`0\` to \`1\` value. \(There's more on this later, in the Math CHOP section\).

\*\(See \*\*/pattern/example3\*\* in the example project file\)\*

This is a great tool for creating lookup tables. \*\(See \*\*/pattern/example4\*\* in the example project file\)\*

\#\#\#\#\# LFO

The LFO CHOP generates an oscillating value according to the parameter settings. It goes back and forth between 2 values that are determined by \`Amplitude\` and \`Offset\`, over a given time, or \`Frequency\`.

\`Frequency\` generally determines how many cycles per second, except when a value is connected to the first input for \`Octave Control\`. If the \`Octave Control\` value is set to \`1\`, the speed is doubled, and if the value is set to \`2\`, the speed is doubled 2 \(4x\), etc.

The shape of the oscillation is controlled by \`Type\`.

You can also oscillate using a different oscilation pattern by using the 3rd input.

\#\#\#\#\# Timer

This CHOP is very useful for anything that involves fixed time periods. You can trigger the timer and recieve different types of data throughout its duration, as well as set it do act different ways when it ends.

The timer can run once and stop at the end, run once and reset itself, repeat itself a certain amount of times, or indefinitely.

Use the \`Timer\` parameter to set the length of the timer, and trigger it to start or reset. You can use \`Delay\` to set an amount of time to wait after the \`Start\` button was triggered, to actually start the timer.

\`Cue Point\` sets a point during the timer that you can jump to by triggering the \`Cue\` pulse. If you'd like to be able to jump to a point that is half way through the duration of the timer, set

On the \`Outputs\` parameter page, you can select what information you would like to recieve. Some common outputs are:

    \* \`Timer Fraction\` displays the percentage of the set time period that has passed, in a 0 to 1 value. 0.5 would mean the timer is half done and 1 meaning the timer is finished.

    \* \`Done\` is a value of \`0\` while the timer is initialized or running, and turns to \`1\` when the timer has finished. It will turn back to \`0\` once the \`Init\` or \`Start\` button is triggered again.

\#\#\#\# Filter CHOPs

\#\#\#\#\# Math

This is probably the most commonly used CHOP. It takes data from its inputs and manipulates it in different ways. Here are some of the useful options:

\#\#\#\#\#\# Mult-Add

\*\(see \*\*example 1\*\* in the math section of the example project file\)\*

You can apply these operations to each of the input values. It functions as you might think it does: 'Pre-Add' happens before the 'Multiply', and 'Post-Add' happens after.

If there is an input value of \`-1.5\`, and Pre-Add value of \`1\`, Multiply value of \`2\`, and Post-Add of \`0\`, the result will be \`-1\`.

With the same input value, but a Pre-Add value of \`0\`, Multiply value of \`2\`, and Post-Add of \`1\`, the result would be \`-2\`.

\#\#\#\#\#\# Range

The \`Range\` page takes all of the input values and either squashes, or spreads the value range according to the settings.

A situation that often occurs is, when you know the value of your input is somewhere between -1 and 1, but you need to scale it to an equivalent proportion from 0 to 100. To do this you would go to the \`Range\` page.

After \`From Range\` you enter \`-1\` and \`1\`

After \`To Range\` you enter \`0\` and \`100\`

If you have an input value of \`-0.5\` the result will be \`2.5\`

If you have an input value of \`1\` the result will be \`10\`

\#\#\#\#\#\# OP

The \`OP\` page offers a lot of different options.

\* \`Combine Channels\` performs the selected operation channel by channel, per operator. If the Math CHOP has more than one CHOP connected to its input, there will be a result for each CHOP. \*\(see \*\*example 2\*\* in the math section of the example project file\)\*

\* \`Combine Chops\` has a selection of the same operations, but applies them between CHOPs that are connected to the input. Using the \`Match By\` selection, it will match the channels and have a result for each channel that has a match. If \`Match By\` is set to \`Channel Name\` and there is a channel that doesn't match, it will be left out of the result.

\* \`Integer\` provides options for rounding.

\#\#\#\#\#\# Scope

On the \`Common\` page there is a field called \`Scope\` which allows you to target certain channels while leaving the other channels untouched.

\#\#\#\#\# Select

This CHOP can be used to split up data that is contained in a single CHOP, or can be used to grab data from a remote section of a project. You can also rename channels that you are selecting at the same time.

If you have a CHOP that contains several channels of information, and need to apply a process to 2 of the channels, but not all, a Select CHOP will allow you to name the channels that you want to focus on. Use the \`Channel Names\` field on the \`Select\` page of the parameters to list the channels you require, separated by a space.

If you want to re-name these channels to something else, you can use the \`Rename From\` field to write the original channel names, and the \`Rename To\` field to enter the new names.

This CHOP also allows you to point to other CHOPs from different areas of a project. Lets say you have have data in a Constant CHOP that is nested inside 2 other COMPs. TheConstant CHOPs path is \`/project1/base1/base1/constant1\`. But your project requires you to access this data in your \`/project1\` COMP. You could either make some \`Out\` CHOPs and manually wire the information, or use a Select CHOP to wireless point at the path of the constant CHOP, which usually quicker and keeps the network more organized. In the \`CHOP\` field of the \`Select\` parameter page, enter \`project1/base1/base1/constant1\`, and you will now see the data.

As before, if there are several channels in the constant, and you only want to select 1, you can use the \`Channel Names\` field to select the one you need, and rename it as well.

\#\#\#\#\# Merge

The Merge CHOP is the opposite of the Select CHOP. It takes channels from multiple CHOPs and merges them into a single CHOP.

The important thing to keep in mind, when combining CHOP channels, is the length \(number of samples\) of each channel as well as when each channel starts and ends. If one of the channels is longer than the others, the shorter channels are extended according to certain parameters contained both in the Merge CHOP as well as the settings of the CHOPs connected to the inputs.

If you have a generator such as a Pattern CHOP, the \`Channel\` parameter page includes \`Extend Left\` and \`Extend Right\` drop down menus. If, further down the operator chain, this channel gets merged with a longer channel, this is how the channel will be handled.

But the \`Merge\` parameter page of the Merge CHOP has settings that can override the extend settings of the input CHOPs.

\* \`Automatic\` uses the input CHOPs settings to handle the extended samples, but if one of the input CHOPs is time-sliced, it will time-slice the rest of the channels that are being merged.

\* \`Extend to Min/Max\` is similar to \`Automatic\`, but if one of the channels is time-sliced, it will extend that from the earliest sample to the last sample of all the channels being input.

\* \`Stretch to Min/Max\` stretches and interpolates the shorter channels to length of the earliest and last samples being input.

\* \`Shift to Minimum\` uses the default extend settings, and moves each channel to line up with the earliest sample of the input channels and extends the end according to the settings of each channel being input.

\* \`Shift to Maximum\` does the same thing, but aligns the last sample of each channel and extends the beginning.

\* \`Shift to First\` shifts each channel to begin at the same sample as the first channel, then trims it to the length of the first channel

\* \`Trim to First\` just crops all channels at the start and end samples of the first channel

\* \`Stretch to First Interval\` stretches or squeezes, and interpolates each channel to the start and end samples of the first channel.

\* \`Trim to the Smallest Interval\` find the channel with the smallest amount of samples, and crops the rest of the channels to it's first and last samples

\* \`Stretch to Smalles Interval\` squeezes all of the channel lengths between the last start sample, and the first end sample. The start and end samples can be from different channels

The dropdown menu \`Duplicate Names\` deals with names of channels that are the same.

\* \`Make Unique\` will generate a new number for each channel that has the same name as a previous channel

\* \`Keep First\` will ignore any channels that have the same name as a previous channel

\* \`Keep Last\` will keep the last channel, and ignore any previous channels that have the same name

\#\#\#\#\# Trail

The Trail CHOP creates a visual display of how the value of it's inputs have changed over a given time. This can be very useful when you need to see subtle differences of a channels movement, or how a channel's value changes compared to another.

\#\#\#\#\# Filter / Lag

Filter and Lag CHOPs create a smooth transition between values over a given time. The 2 CHOPs have similar purposes, but different options.

Filter CHOP applies a smoothing effect or time, and you can choose the shape of the smoothing, with different options for different shapes.

\*\(see \*\*/filter\_lag/ example 1\*\* of the example project file\)\*

Lag CHOP, depending on the method of smoothing, allows you to set 2 seperate effect-lengths for an increasing input value, and decreasing input value.

\*\(see \*\*/filter\_lag/ example 2\*\* of the example project file\)\*

\#\#\#\#\# Trigger

This CHOP takes an event, such as a pulse, and creates an ADSR envelope \(Attack, Decay, Sustain, and Release\) with some additional control.

Here is a Trail CHOP that has recorded the shape of an envelope:

The envelope can be triggered by the \`Trigger Pulse\` on the \`Trigger\` Parameter page, or by connecting a CHOP to its input, such as the Out of a Button.

The different sections of the envelope can have easings as well.

Here is an example of with the \`Attack Shape\` set to \`Ease out\`, \`Decay Shape\` set to \`Ease in Ease out\` and the \`Release Shape\` set to \`Ease in\`:

