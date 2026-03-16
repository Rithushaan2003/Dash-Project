# Step 8 – Mean Opinion Score (MOS) Evaluation (ITU‑T BT.500)
The Mean Opinion Score (MOS) is a subjective video‑quality rating method defined in ITU‑T BT.500.
The same video clip was played under the streaming conditions from Step 4 and Step 5, and the perceived quality was rated using the standard 1–5 MOS scale:

• 	5 – Excellent (no visible impairments)

• 	4 – Good (slight impairments, not annoying)

• 	3 – Fair (noticeable but acceptable impairments)

• 	2 – Poor (annoying impairments)

• 	1 – Bad (very annoying / unwatchable)

The MOS score was assigned based on observed smoothness, freezing, buffering, and visual artifacts.

---

## MOS Results
| Scenario | Observed Behaviour | MOS |
|---------|--------------------|-----|
| Step 4 – DASH Adaptive Streaming | Smooth playback, minimal stutter | 4–5 |
| Step 5 – Bitmovin Player (Non‑Adaptive Streaming) | Repeated short freezes (freeze → play → freeze → play) | 3–4 |

---

## Conclusion

• Adaptive streaming (Step 4) maintained high video quality with minimal issues.

• The Bitmovin Player (Step 5), using non‑adaptive streaming, experienced repeated short freezes, reducing the perceived quality.

• These results highlight the advantage of adaptive bitrate streaming for maintaining smooth playback.
