The code basicly implements the concepts such as:
1. Utilizing frontier llms model (GPT & Claude) API
2. Utilizing tool function of Claude
3. Utilizing OpenAI multi modal services in image & voice
4. Utilizing Gradio as a tool to build robust application in a lightning speed

 
PSEUDOCODE:
- User must first greet the examiner using their microphone
- Examiner (GPT) will greet and proceed with the speaking session with the examinee via TTS service
- The communication loop between user and examiner (GPT) begins
  - Counter starts at 0
  - For each interaction:
    - Examiner asks a question via TTS
    - User responds via microphone
    - Counter++
  - Loop continues until counter reaches 4

- WHEN counter equals 4:
  - The complete communication history between user & examiner is passed to Appraiser (Claude)
  - The Appraiser analyzes each of the user's interactions with the examiner

- FOR each user interaction:
  - IF the user's response aligns with the examiner's question:
    - Add 1 point to score
  - ELSE:
    - Subtract 1 point from score
    
- Appraiser (Claude) calculates total score (range from -4 to 4)
- Appraiser (Claude) triggers tool_use
- The tool_use function substitutes the numerical score into a predefined category (excellent, very good, good, pass, practice more)
- Category and score are then passed to the image generation (GPT) service
- User receives their certificate based on their speaking performance
