# The party-scene prompt

This is the prompt **Burning Bridges AI** sends to ByteDance Seedance 2.5, verbatim —
the same text on every render. Two things change with the settings:

| What is substituted | Value |
| --- | --- |
| The ratio sentence in `OUTPUT` | `vertical 9:16 framing for TikTok, Reels and Shorts` or `landscape 16:9 framing` |
| `20 seconds` in `OUTPUT` | the length you ask the model for; the beat timings below are written to 20.09 seconds |

The photo travels as a **reference image** (`reference_image_urls`). The track
travels as a **reference audio** (`reference_audio_urls`) and is *also* attached to
the finished file afterwards — the vendor does not pass a reference audio through,
which is measured in [`docs/audio-findings.md`](../docs/audio-findings.md).

The prompt is the product. Paste it whole; do not trim the action sequence, the
timings are what make the 20 beats land on the beat.

---

```text
CAMERA
Live-action photorealistic party video, 30fps, one single continuous handheld take, no cuts. The camera is handheld at chest height, close to the character, drifting and orbiting slightly with subtle shake, keeping the character centred the whole time. Shallow depth of field on the character, with the crowd and the room readable behind.

INPUTS
Reference photo = the identity source for the main character. It may show a man, a woman, or an animal.

IDENTITY LOCK — THE MOST IMPORTANT RULE
The main character's face must match the reference photo exactly and must stay identical in every frame of the video. The hairstyle, hair length, hair colour and hairline must match the reference photo exactly and must not change at any point.

IF THE SUBJECT IS AN ANIMAL
Keep the animal's species, head shape, face, coat colour, markings and fur exactly as photographed. The same action sequence is performed by the animal in a playful anthropomorphic style, using its own paws, limbs or mouth to hold and raise the cup, keeping its natural animal face and proportions throughout. Do not turn the animal into a human, and do not put a human face on it.

CLOTHING RULE
Look at the reference photo. If clothing is visible in the photo, keep that exact clothing on the character for the whole video, unchanged. If no clothing is visible in the photo, dress the character automatically in clean, modest, casual party clothing that matches the atmosphere of the scene: a light-coloured oversized t-shirt or top with casual trousers or shorts, contemporary and effortless. In both cases the clothing must stay consistent for the whole video and must never change mid-shot.

ABSOLUTE CONTENT RULE
Strictly no nudity, no partial nudity, no exposed chest, midriff, buttocks or underwear, no transparent or see-through clothing, no sexualised posing, no suggestive movement, no sexual content of any kind. The character is fully and modestly dressed in every single frame. This rule overrides everything else.

SCENE
An upscale private party room at night: dark wood-panelled walls, a large crystal chandelier overhead, a long bar-height table with green LED under-lighting, platters of food, fruit and bottles. Teal-green accent lighting on the walls mixed with warm chandelier light from above. Behind the main character, a crowd of about twenty people dances and cheers. On the right, a woman with her hair in two space buns holding a glass. The main character stands centre frame, chest-up, holding a cup.

ACTION SEQUENCE — MUST MATCH THE REFERENCE EXACTLY
Every gesture below lands on a beat. Do not invent new moves, do not skip a move, do not reorder them, do not free-style.

1. 0.00-0.97s — Leaning side to side with the beat, one arm extended out to the side, cup in the other hand. The crowd behind dances.
2. 0.97-1.90s — Turning the upper body toward the camera, bringing the cup in to chest height, nodding on the beat, smiling.
3. 1.90-2.37s — Leaning toward the lens and waving the free hand close to the camera.
4. 2.37-3.29s — Straightening up, mouth open singing along, cup held in front of the chest.
5. 3.29-3.76s — Lifting the cup to shoulder height and pointing with the free hand.
6. 3.76-4.69s — Raising the cup higher and sweeping the free arm across the chest, hips swaying.
7. 4.69-6.54s — Continuing to dance in place, cup held up, turning the head to look around at the crowd and laughing.
8. 6.54-7.47s — A big arm move: the free arm throws out to the side and swings down and across the body, cup raised in the other hand.
9. 7.47-8.86s — Repeating that swing with more force, body turning left and right, crowd dancing along.
10. 8.86-10.25s — Bending the arm and bringing the free hand up near the face, eyes closing, swaying.
11. 10.25-11.18s — Raising the cup high above shoulder height with both hands, head tilted slightly back.
12. 11.18-12.11s — Turning to the woman on the right with the space buns and extending the cup toward her; the two cups meet and clink.
13. 12.11-13.04s — Clinking a second time, both laughing.
14. 13.04-14.43s — Holding the cup up toward her, both arms open, celebrating.
15. 14.43-14.89s — Turning back to the camera, lowering the cup, laughing.
16. 14.89-15.82s — Pointing the index finger straight at the camera, cup in the other hand.
17. 15.82-16.75s — Raising the cup to the face and drinking, the cup covering the lower half of the face.
18. 16.75-17.68s — Lowering the cup, head tilted, smiling at the camera.
19. 17.68-18.61s — Waving the free hand at the camera, then raising both hands, big smile.
20. 18.61-20.09s — Full cheer: both arms open and up, mouth open celebrating, and the whole crowd behind raises their arms and cheers.

AUDIO
The soundtrack is supplied. Use it exactly as given and let it drive the timing: the music is 129.3 BPM with one beat every 0.464 seconds.
The supplied track must be the ONLY audio in the video. Do not generate music, do not add ambience, do not add crowd noise, cheering, clapping or laughter as sound, and do not add speech, singing or any other audio of any kind. The rendered file's soundtrack is the supplied track and nothing else.

STYLE
Photorealistic live-action footage, natural skin texture, natural body weight and physics, believable fabric movement, practical party lighting with real highlights on skin, 35mm film grain, slight handheld imperfection, realistic crowd motion blur. Consistent lighting direction for the whole shot. No look of CGI, no animation, no illustration.

DELIVERY
No on-screen text, no captions, no subtitles, no watermarks, no logos.

OUTPUT
A single continuous shot, vertical 9:16 framing for TikTok, Reels and Shorts, 20 seconds total, with the supplied track as its only audio. The full sequence must not run beyond 20 seconds.
```
