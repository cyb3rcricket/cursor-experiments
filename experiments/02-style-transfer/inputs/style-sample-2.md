Same prompt. Three wizards.

Gemini spent complexity on the art. Astra spent it on efficiency. Grok spent it on machinery — and then gave me that wizard.

I threw the same assignment at three models:

    Gemini 3.8 Flash High
    GPT-6 Astra Light
    Grok 4.7 Extra High

The prompt came from a public experiment by Majid Manzarpour: an animated pixel-art wizard, pure code. I kept the constraints the same on purpose. I wanted to see what each model would decide was worth the extra complexity.

First impression, before I opened the files: Astra built it with about half the code. Gemini looked the best. Grok looked horrible. None of them were a finished game. That was fine. I was not grading “wow.” I was grading where the effort went.
They all did the assignment

This is the part that surprised me. All three implemented almost the entire spec:

    128×96 offscreen canvas
    24-color palette
    Pixel snapping
    4-state animation
    Fixed 60Hz simulation
    Pooled particles
    Staff / arm / head / robe pose parameters
    Charge spiral
    Projectile
    Screen shake
    Rim lighting

So the interesting question is not “who followed instructions.” They all did. The interesting question is why they still feel like three different objects.
The numbers
Model 	Lines 	Size 	What it seemed to buy
Gemini 3.8 Flash 	1,042 	36.7 KB 	The picture
GPT-6 Astra 	612 	21.0 KB 	The same architecture, cheaper
Grok 4.7 	924 	23.0 KB 	Machinery

Astra is the engineering result I keep turning over. Nearly the same system. 612 lines. Still looked decent. Not bad.

Grok’s code is actually pretty sophisticated: compiled pixel runs, a cached background, typed-array particles, precomputed rim geometry. That is real machinery. And somehow it still made the ugliest wizard.

Gemini wrote the most code and the largest file, and it also looked the best. It seems to have spent more of its complexity on actually authoring the visual result instead of building a nicer engine behind a worse picture.
Then I watched them back to back

Staring at the files hides the difference. The clips do not.
01 · Gemini 3.8 Flash High

Leaned hardest into the visuals.
02 · GPT-6 Astra Light

Almost the same job, dramatically less code.
03 · Grok 4.7 Extra High

Clever machinery. That wizard. 😂

The videos are on the comparison post. I am keeping them there for now instead of hotlinking X’s CDN from a local site.

If you watch them without the labels: which one would you ship?
What I think this is actually measuring

Not benchmark scores. Not “who is best at code.” Something narrower:

When the spec is already full, where does the model spend the leftover budget?

Gemini spent it on the art.

Astra spent it on efficiency.

Grok spent it on machinery.

That tracks with how I already pick tools. I do not need one model to win every category. I need to know what it will over-invest in when I am not looking. If I want a picture people can feel, I do not want the model that built the most impressive particle pool and then forgot the robe. If I want a small system I can keep reading, Astra’s half-size file is the more interesting artifact.

Also worth saying out loud: Gemini looked the best, and it still was not amazing. A bake-off can be useful without producing a masterpiece. The failed wizard is part of the evidence.
Why this belongs on the shelf

This started as a few X posts in one evening. I am putting the long version here because the takeaway is the thing I want to keep:

Same prompt is not the same product. The model’s taste shows up in what it overbuilds.

More bake-offs later. Next time I might keep the visual spec even meaner, or ask for the smallest file that still reads as a wizard from two meters away. The constraint is the experiment.

First posted in pieces on Sep 24 and Sep 25, 2026. Prompt credit: @majidmanzarpour. 