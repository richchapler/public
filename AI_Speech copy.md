# Lab: AI Speech

<img src="..\images\AI_Speech\AI_Speech_Header.png" width="1000" />

## Introduction

Azure AI Speech is a cloud-based service from Microsoft that leverages advanced algorithms to process and understand spoken language, extracting valuable insights and enabling dynamic communication solutions. It encompasses a range of capabilities—from real-time speech-to-text transcription and speaker recognition to lifelike text-to-speech synthesis and multilingual translation—all designed to solve real-world problems quickly and effectively.

<!-- ------------------------- ------------------------- -->

## Exercise 1: Prepare Resources  

### Azure

- **Speech Services**: 
  - Pricing Tier `Standard S0`, 
  - Supported Region (**West US 2**, West Europe, Southeast Asia, South Central US, Sweden Central, North Europe, East US 2)

### On-Prem

> Additional content (e.g., PowerShell, Visual Studio Code, etc.) pending work on **Low Code** sections

<!-- ------------------------- ------------------------- -->

## Exercise 2: Speech Capabilities by Scenario

### Captioning with Speech to Text

<!-- ------------------------- ------------------------- -->

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Speech capabilities by scenario** >> **Captioning with speech to text**.

<img src="..\images\AI_Speech\SpeechStudio_Captioning_TryItOut.png" width="800" title="Snipped April, 2025" />

On the **Try it out** >> **Sample videos** tabs, click **Real-time captioning**, and then scroll down on the page.

<img src="..\images\AI_Speech\SpeechStudio_Captioning_RealTime.png" width="800" title="Snipped April, 2025" />

Click the Play button the video and observe captioning.

<!-- ------------------------- -->

##### Captioning Settings

...detailed on the right side of the interface and include the following parameters:

- **Recognition event**: `--realTime`  
  Enables real-time mode, which returns stable partial results as audio is processed live.

- **Stable partial result threshold**: `--threshold 3`  
  Default value is 3. This determines how many recognized words must be repeated before the result is considered stable enough to show. Higher values increase stability but delay appearance.

- **Maximum caption length (character)**: `--maxLineLength 60`  
  Sets the character limit per line for each caption. Default is 60.

- **Maximum number of caption lines**: `--lines 2`  
  Controls how many lines of text can appear simultaneously in the caption block.

- **Profanity masking**: `--profanity mask`  
  Masks any profane words detected during transcription using asterisks or similar characters.

- **Phrase list**: `--phrases "neural TTS;Cognitive Services"`  
  Custom phrase list to improve recognition of domain-specific terms or phrases. Items are semicolon-separated.

<!-- ------------------------- -->

###### Example #1: Live Event Broadcasting 
> For high-energy, fast-paced content where low latency matters (e.g., sports event).
> - `--realTime`: stream captions as the speaker talks  
> - `--threshold 2`: fast response, lower stability  
> - `--maxLineLength 50`: fits cleanly on screen overlays  
> - `--lines 2`: prevents crowding the display  
> - `--profanity mask`: keeps output appropriate for public viewing  
> - Phrase list: team names, campus locations, event-specific terms

###### Example #2: Corporate Meeting 
> Simulates real-world business environments where clarity and professionalism are key.
> - `--realTime`: supports live note-taking  
> - `--threshold 3`: balances speed and stability  
> - `--maxLineLength 60`: improves readability in transcripts  
> - `--lines 2`: clean format for screen share overlays  
> - `--profanity mask`: appropriate for formal settings  
> - Phrase list: project names, department acronyms, business terms

###### Example #3: Classroom (accessibility focus)
> Helps support learning environments with better readability and accuracy.
> - `--realTime`: enables live following of lectures  
> - `--threshold 4`: prioritizes accuracy, reduces caption flicker  
> - `--maxLineLength 60`: allows complete sentences  
> - `--lines 3`: gives room for full thoughts in captions  
> - `--profanity raw`: keeps educational integrity  
> - Phrase list: lecture terms, instructor names, course-specific vocab

<!-- ------------------------- ------------------------- -->

#### Offline Captioning

Scroll up on the page, and then click **Offline captioning**

<img src="..\images\AI_Speech\SpeechStudio_Captioning_Offline.png" width="800" title="Snipped April, 2025" />

Click the Play button and observe captioning.

##### **Real-Time vs. Offline Captioning**

Offline captioning differs from real-time captioning in **timing, processing, and result stability**.

| Aspect | Real-Time Captioning | Offline Captioning |
| :--- | :--- | :--- |
| **Timing** | Captions are generated and displayed live as the person speaks | Captions are generated after the full audio/video is available |
| **Result Type** | Partial results shown, may change mid-sentence | Final, stable transcript is used |
| **Use Case** | Live broadcasts, streams, webinars | Pre-recorded videos, films, audio before release |
| **Editing** | Limited (real-time only) | Can adjust caption formatting, timing, and content before publishing |
| **Stability** | May revise words after initial appearance | No revisions — output is final |

------------------------- -------------------------

### Post Call Transcription and Analytics

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Speech capabilities by scenario** >> **Post Call Transcription and Analytics**.

<img src="..\images\AI_Speech\SpeechStudio_Transcription_TryItOut.png" width="800" title="Snipped April, 2025" />

On the **Try it out** >> **Try with samples** tabs, click **Apply for a loan**, and then scroll down on the page. Default selection is the **Analyze sentences** tab.

<img src="..\images\AI_Speech\SpeechStudio_Transcription_AnalyzeSentences.png" width="800" title="Snipped April, 2025" />

Review sample content:

- **Audio Player**: A simple media bar with play/pause controls and a visible duration (e.g., 03:02s)
- **Transcript Content**: Simulated dialogue from a customer support call demonstrates live transcription, redaction, and sentiment tagging.
  - **Sentiment**: Each transcript line is tagged on the left with an evaluation of sentiment (e.g., Positive, Neutral, etc.)  
  - **Speakers**: Transcript lines are grouped and labeled by speaker (e.g., Speaker1, Speaker2) with timestamps
  - **PII Masking**: Sensitive information (e.g., names) is redacted and replaced with asterisks (e.g., ****), with labels like **Name** underneath 
- **Hide PII Toggle**: A switch in the upper right of the transcript section allows turning PII masking on or off
- **Call Summary Tab**: A second tab, **Call summary**, is visible but not selected, likely for higher-level insights

Try other Scenario Cards (e.g., **Signing up for Insurance**).

------------------------- -------------------------

### Live Chat Avatar

<!-- ------------------------- ------------------------- -->

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Speech capabilities by scenario** >>  **Live Chat Avatar**.

<img src="..\images\AI_Speech\SpeechStudio_Avatar.png" width="800" title="Snipped May, 2025" />

<!-- ------------------------- -->

##### Try with sample

On the **Try with sample** tabs, click the Play button the video and observe the live chat sample.

<img src="..\images\AI_Speech\SpeechStudio_Avatar_TryWithSample.png" width="800" title="Snipped May, 2025" />

###### Settings

...detailed on the right side of the interface and include the following parameters:

- **Language**: `English (United States)`  
  Specifies the language used for speech synthesis and understanding during the interaction.

- **Voice**: `Sara`  
  Selects the synthetic voice used by the avatar for spoken responses. "Sara" is one of the standard voice personas available.

- **Speaking style**: `Friendly`  
  Modifies the tone and inflection of the voice to sound warm and approachable, appropriate for customer-facing scenarios.

- **Conversation style**: `"You are a voice assistant, and when you answer questions, your response should not exceed 25 words."`  
  Provides prompt-level control over the avatar’s response behavior—limiting verbosity and guiding tone to simulate a concise support agent.

- **Avatar**: `Lisa-casual-sitting`  
  Specifies the visual representation of the avatar, in this case a casual seated female persona used for customer support roles.

- **Sample response**:  
  `"Yes, Microsoft offers special discounts and pricing for students and educators on the Surface Go and other devices through their Education Store."`  
  Demonstrates how the avatar responds to a question using the configured voice, style, and character.

<!-- ------------------------- -->

##### Try on your own

On the **Try on your own** tab, try different questions, settings, voices, and avatars.

<img src="..\images\AI_Speech\SpeechStudio_Avatar_TryOnYourOwn.png" width="800" title="Snipped May, 2025" />

###### Settings

- **Language**: `English (United States)`  
  Sets the primary language for both input and synthesized speech. This determines pronunciation, transcription, and voice selection defaults.

- **Multi-language**: Toggle is set to `Off`  
  When enabled, this allows the avatar to automatically detect and respond in multiple languages during conversation.

- **Voice**: `Ava Multilingual`  
  Specifies the synthetic voice used by the avatar. "Ava Multilingual" supports dynamic language shifts when paired with multi-language input.

- **Speaking style**: `Default`  
  Sets the vocal tone and delivery style; can be adjusted to styles like cheerful, angry, or empathetic where supported.

- **Model**: `GPT-4o` (grayed out but labeled)  
  Indicates that the GPT-4o model is selected for language generation, though selection may be locked to this choice.

- **Response style**: `Default`  
  Governs the formatting and verbosity of the generated replies. Useful for tuning tone to formal, concise, or creative.

- **Prompt / System Message**: `You are an intelligent assistant.`  
  Provides the system prompt for controlling assistant behavior, tone, and personality.

- **Avatar**: Three male avatars shown (e.g., business casual, bright red sweater, blue dress shirt)  
  Allows the user to visually customize the avatar’s appearance to match different use cases or brand identities.

- **Mic Interaction**: "Press the mic to start talking"  
  Enables live voice input, letting the user speak naturally with the avatar using their microphone.

------------------------- -------------------------

### Language Learning

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Speech capabilities by scenario** >>  **Language Learning**.

<img src="..\images\AI_Speech\SpeechStudio_Language.png" width="800" title="Snipped May, 2025" />

<!-- ------------------------- -->

##### Try it out

<img src="..\images\AI_Speech\SpeechStudio_Language_TryItOut.png" width="800" title="Snipped May, 2025" />

On the **Try it out** tab, chat with your language teacher, then click **Assess my response**, and then review the produced report:

- **Pronunciation Score**: `78`
  <br>Shown in a circular gauge with a legend color-coded for ranges 0 to 59 (red), 60 to 79 (yellow), and 80 to 100 (green)

- **Pronunciation Breakdown**: `Accuracy Score 79 / 100`, `Fluency Score 81 / 100`, `Prosody Score 77 / 100`
  <br>Progress bars detail the specific metrics contributing to the overall pronunciation score

- **Content Score**: `10`
  <br>Displayed in a circular gauge using the same three-range color legend to indicate content performance

- **Content Breakdown**: `Grammar Score 10 / 100`, `Vocabulary Score 10 / 100`
  <br>Progress bars highlight low performance in grammar and vocabulary aspects

- **Feedback Button**: `Get feedback on how to improve`
  <br>Provides targeted suggestions and guidance to improve both pronunciation and content scores

------------------------- -------------------------

### Video Translation

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Speech capabilities by scenario** >> **Video Translation**.

<img src="..\images\AI_Speech\SpeechStudio_VideoTranslation.png" width="800" title="Snipped May, 2025" />

Click **+ Create a project**

<!-- ------------------------- -->

###### New Project

<img src="..\images\AI_Speech\SpeechStudio_VideoTranslation_NewProject.png" width="800" title="Snipped May, 2025" />

Review / modify settings:

- **Voice type**: `Prebuilt neural voice`
  <br>Automatically matches prebuilt neural voices similar to the speakers in your video.
  <br>Switch to **Personal voice** if you have access to create a custom voice for the original speakers.

- **Video file**: drag-and-drop area or "Browse files…" (`.mp4`, `.mp3` or `.wav`; under 500 MB and 60 minutes)
  <br>Uploads the source media to be transcribed, translated and dubbed.

- **Project name**: `Enter a name for your file`
  <br>Assigns a descriptive title to your translation project.

- **Number of speakers**: `1` (Auto detect On)
  <br>Specifies how many distinct voices appear in the file; automatic speaker count can be toggled on or off.

- **Language of the video**: `Auto detect`
  <br>Selects the input language for transcription; auto detect supports a limited set of languages.

- **Translate to**: `English (United States)`
  <br>Chooses the target language and locale for the translated audio output.

- **I acknowledge that video translation will incur usage charges to my account, effective from June 2024**: checkbox
  <br>Confirms you understand the billing implications before proceeding.

- **Accept code of conduct for Azure AI Speech text to speech**: checkbox
  <br>Indicates your agreement with the service’s usage policies.

- **Next: Advanced settings**: button
  <br>Opens an additional pane for fine-tuning recognition, translation and synthesis options.

...and, then click **Create**. Allow time for upload and processing.

------------------------- -------------------------
------------------------- -------------------------

## Exercise 3: Speech to Text

### Real-Time Speech to Text

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Speech to text** >> **Real-time speech to text**.

<img src="..\images\AI_Speech\SpeechStudio_RealTimeSpeechToText.png" width="800" title="Snipped May, 2025" />

On the **Try it out** tab, click the microphone, speak, and review the produced text.

<!-- ------------------------- -->

##### Interface Elements

* **Resource acknowledgement checkbox**: `I acknowledge that this application uses the resource {prefix}ss and will incur usage of my account` <br>Confirms you understand the billing implications for the selected Azure resource.

* **Language dropdown**: `English (United States)`<br>Selects the input language for real-time transcription.

* **Advanced options link**: `Show advanced options` <br>Expands additional settings:

  * **Language identification**: `Off` toggle <br>Automatically detect the spoken language when enabled.

  * **Language identification mode**: `At start` / `Continuous` radio buttons <br>Select whether detection runs once at the beginning or continuously throughout the session.

  * **Speaker diarization**: `Off` toggle <br>Segment and label the transcript by speaker when enabled.

  * **Custom endpoint dropdown**: `[None]` <br>Choose one of your custom speech-to-text endpoints to drive the transcription.

  * **Output format dropdown**: `Detailed` <br>Select the JSON verbosity level: "Simple" for plain text or "Detailed" for word-level timestamps and confidence scores.

  * **Phrase list**: `Off` toggle <br>Enable to supply domain-specific words or phrases to boost recognition accuracy.

  * **Phrase list text field**: (disabled) <br>Once the phrase list is turned on, enter comma- or semicolon-separated terms here.

  * **Hide advanced options link**: `Hide advanced options` <br>Collapse this panel to return to the basic view.

* **Audio input panel**: `Drag and drop audio file(s) here` / `Browse files…` / `record audio with a microphone` <br>Allows you to upload or capture audio for transcription.

* **Test results metadata**: `File name: 20250401_141328.wav`, `Language: English (United States)`, `Custom endpoint: [None]` <br>Shows details about the currently loaded audio sample.

* **Playback controls**: Play button / progress slider / elapsed time display <br>Enables audio playback and lets you see the transcript timing.

* **Transcript view tabs**: `Text`, `JSON` <br>Toggle between the human-readable transcript and the detailed JSON output.

* **Live transcript display**: (live text area) <br>Shows recognized speech in real time as the audio is processed.

* **Transcription settings indicators**: `Output format: Detailed`, `Phrase list: Off`, `Speaker diarization: No` <br>Summarizes the active configuration for your transcription.

* **Download transcript icon**: download arrow <br>Lets you save the transcript or JSON results locally.

------------------------- -------------------------

### Whisper Model in Azure OpenAI Service

> [Whisper](https://openai.com/index/whisper/) is OpenAI’s speech recognition solution. It is available in a limited number of Azure regions {e.g., East US 2}.

<!-- ------------------------- -->

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Speech to text** >> **Whisper Model in Azure OpenAI Service**.

<img src="..\images\AI_Speech\SpeechStudio_WhisperModel.png" width="800" title="Snipped May, 2025" />

On the **Try it out** tab, upload an audio file and review the produced text.

<!-- ------------------------- -->

##### Interface Elements

* **Resource dropdown**: `{prefix}oai (OpenAI, East US 2, S0)` <br>Select which Azure OpenAI resource to drive the demo.

* **Deployment dropdown**: `whisper` <br>Pick the name of your Whisper-v2-large deployment under the selected resource.

* **Cost acknowledgement**: checkbox `I acknowledge that running this demo will incur usage and may incur costs to my Azure resources.` <br>Must be checked to proceed, confirming you understand billing implications.

* **Mode selector**: `Transcribe` / `Translate` (Transcribe selected) <br>Choose whether to get a transcript in the original language or a translation into English.

* **Language identification**: toggle `On` <br>Automatically detect the spoken language before transcription.

* **Language dropdown**: `English` (disabled) <br>Shows detected or selected language; locked when identification is on.

* **Temperature slider**: `0.3` <br>Adjusts randomness in the model’s transcription output.

* **Temperature value**: numeric input `0.3` <br>Precise numeric representation of the slider setting.

* **Prompt text area**: placeholder "An optional text to guide the model’s style or continue a previous audio segment. The prompt should be in English." <br>Supply context or domain cues to steer transcription style.

------------------------- -------------------------

### Batch Speech to Text

<!-- ------------------------- -->

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Speech to text** >> **Batch speech to text**.

<img src="..\images\AI_Speech\SpeechStudio_BatchSpeechToText.png" width="800" title="Snipped May, 2025" />

On the **Try it out** tab, upload an audio file and review the produced transcription.

<!-- ------------------------- -->

##### Interface Elements

* **Language of audio dropdown**: `Spanish (Mexico)`
  Selects the input language for transcription.

* **Model dropdown**: `20241203`
  Chooses which speech model version to use.

* **Model to compare (optional) dropdown**: `None`
  Optionally select a second model for side-by-side accuracy comparison.

* **"Show advanced options" link**
  Toggles display of further configuration settings.

  * **Language identification**: `Off`
    When enabled, automatically detects multiple languages spoken in the audio; reveals a language-selection dropdown.

  * **Speaker diarization**: `No`
    Toggles whether the service separates and labels distinct speakers in the transcript.

  * **Maximum number of speakers**: `2`
    When speaker diarization is on, limits how many unique speakers to identify.

  * **Profanity filter mode**: `Masked`
    Controls handling of profane words (options include Masked, Removed, Raw).

  * **Punctuation mode**: `DictatedAndAutomatic`
    Determines whether to insert punctuation automatically in addition to honoring any dictated punctuation.

  * **Display form word-level timestamps**: `Yes`
    Includes start times and durations for each word in the output transcript.

  * **Lexical form word-level timestamps**: `No`
    Includes timing metadata for the lexical (normalized) form of each word.

* **Use with your resource checkbox**: checked
  Acknowledges that the selected Azure Speech resource (`prefixss (Speech Services, West US 2, S0)`) will incur billing; includes "Choose a different resource" link.

* **Upload audio files pane**
  Container for file inputs with two tabs:

  * **Local file tab** (active)
    Shows a drag-and-drop area plus "Browse files…" link.

  * **Web URLs tab**
    Allows you to paste one or more SAS-secured URLs.

* **Drag-and-drop area**
  "Drag and drop files Or Browse files…" for local upload (`.mp3`, `.wav`, etc.).

* **Batch jobs list**
  Displays existing job IDs as links (e.g. `20250515_120228`), each with:

  * **Radio button** to select the job
  * **Retry icon** (circular arrow)
  * **Delete icon** (trash can)

* **Clear all link**
  Empties the batch jobs list.

* **Job details pane**
  When a job is selected, shows its status (e.g. "Transcribing …") and the files included (e.g. `TryOutOriginal.mp4`).

------------------------- -------------------------

### Custom Speech

With custom speech, you can evaluate and improve the accuracy of speech recognition for your applications and products.

[What is custom speech?](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/custom-speech-overview)

<!-- ------------------------- -->

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Speech to text** >> **Custom speech**.

<img src="..\images\AI_Speech\SpeechStudio_CustomSpeech.png" width="800" title="Snipped May, 2025" />

Review the documentation, linked content, and video.

------------------------- -------------------------

### Pronunciation Assessment with Speech to Text

<!-- ------------------------- -->

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal), and log in with your Azure credentials.

<img src="..\images\AI_Speech\SpeechStudio_SpeechToText.png" width="800" title="Snipped May, 2025" />

Click **Speech to text** >> **Pronunciation Assessment with speech to text**.

<img src="..\images\AI_Speech\SpeechStudio_PronunciationAssessment.png" width="800" title="Snipped May, 2025" />

<!-- ------------------------- -->

##### Reading

Try the different samples and see how you score.

<img src="..\images\AI_Speech\SpeechStudio_PronunciationAssessment_Reading.png" width="800" title="Snipped May, 2025" />

##### Interface Elements

* **Language dropdown**: `Choose a Pronunciation Assessment language`
* **Show advanced options**: link
  * **Enhanced add-on settings**: `Prosody assessment`
    Enables the optional prosody module to score rhythm, stress and intonation in your reading.
* **Sample text tabs**:

  * `Sample 1`, `Sample 2`, `Sample 3`, `Sample 4`, `Enter your own`
* **Script panel**: scrollable area showing the selected passage.
* **Audio input pane** (two columns):

  * **Record**: microphone button labeled "Record audio with a microphone"
  * **Upload**: drag-and-drop area plus `Browse for a file`

<!-- ------------------------- -->

#### Speaking

Choose a sample topic, record, and see how you score.

<img src="..\images\AI_Speech\SpeechStudio_PronunciationAssessment_Speaking.png" width="800" title="Snipped May, 2025" />

##### Interface Elements

* **Language to assess**: `English (United States)`
* **Sample topics**: 'Talk about your day today' + `Enter your own topic` link
* **Show advanced options**: link
  * **Enhanced add-on settings**: `Prosody assessment`, `Content assessment`

* **Prompt banner**: title and instruction text
* **Recording card**:
  * Microphone button with "Press the mic to start talking"
  * Recommended guidelines below (minimum seconds, words, sentences)

<!-- ------------------------- -->

#### Gaming

Choose a tongue twister, record, and see how you score.

<img src="..\images\AI_Speech\SpeechStudio_PronunciationAssessment_Gaming.png" width="800" title="Snipped May, 2025" />

##### Interface Elements

* **Header banner**: `Tongue twister`
* **Generate new twister**: button
* **Twister text**: displayed sentence with audio-play icon
* **Recording button**: central microphone icon
* **Playback scrub bar**: play control, timeline slider, elapsed time
* **Assessment metrics**: labeled counters for
  * Omissions
  * Mispronunciations
  * Insertions
  * Unexpected break
  * Missing break
  * Monotone

------------------------- -------------------------

### Speech Translation

<!-- ------------------------- -->

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Speech to text** >> **Speech Translation**.

<img src="..\images\AI_Speech\SpeechStudio_SpeechTranslation.png" width="800" title="Snipped May, 2025" />

Record a phrase and review translation (both text and audio).

##### Interface Elements

* **Usage acknowledgement**: checkbox (checked)
  "I acknowledge that this application uses the resource prefixss and will incur usage of my account." Includes a "Choose a different resource" link.

* **Choose a spoken language**: `English (United States)`
  Dropdown to select the input audio language for translation.

* **Choose a target language**: `Filipino`
  Dropdown to select the output translation language.

* **Speak out translation**: toggle (On) with **Voice name**: `Blessica (fil-PH-BlessicaNeural)`
  When enabled, plays back the translated audio using the selected neural voice.

* **Choose audio files** pane:
  * **Drag and drop area** or **Browse files…** link
  * **Record audio with a microphone** button
    Uploads or captures source audio for translation.

* **Audio files list**: each entry shows a file name (e.g. `20250404_131638.wav`), a success checkmark, a retry icon, and a delete icon.

* **Test results** pane:
  * Metadata header: **File name**, **Target language**, **Language**, **Voice name**
  * **Playback control**: play button, progress slider, elapsed time, download link
  * **Result tabs**: `Translated text` / `Original text` / `JSON`
  * **Translated text area**: displays the translated transcript
  * **Play translation** button, download icon, and copy-to-clipboard icon beneath the transcript.

------------------------- -------------------------
------------------------- -------------------------

## Exercise 4: Text to Speech

### Voice Gallery

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Text to speech** >> **Voice Gallery**.

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_VoiceGallery.png" width="800" title="Snipped May, 2025" />

Browse available voices.

##### Interface Elements

* **Voice catalog**

  * **Search box**: placeholder `Search`
    Filters the gallery by voice name or keyword.

  * **Language dropdown**: `English (United States)`
    Selects which locale’s voices to display.

  * **Sort by dropdown**: `Recommendation`
    Ordering options (e.g. Recommendation, Alphabetical).

  * **Show only pinned**: checkbox
    Toggles display of your pinned favorites.

  * **Voice count**: `97 voices`
    Shows the number of matching voices.

  * **Filter** (collapsible):
    * **Gender**: `Female`, `Male`, `Neutral`
    * **Age group**: `Child`, `Young Adult`, `Adult`, `Senior`
    * **Capability**: `Context-aware`, `Multi-lingual`, `Multi-style`
    * **Voice type**: `Neural`, `Neural HD`
    * **Recommendation**: `Featured`, `Popular`
    * **Speaking style**: tags like `Affectionate`, `Cheerful`, `Conversation`, etc., with a `More` link
    * **Personality**: tags like `Animated`, `Approachable`, `Confident`, etc., with a `More` link
    * **Tailored scenario**: tags like `Audiobook`, `Gaming`, `Podcast`, etc., with a `More` link
    * **Source**: e.g. `OpenAI`, `Microsoft`

  * **Voice cards grid**:
    Each card displays a voice entry with:
    * **Voice name** (e.g. `AriaNeural`)
    * **Locale label** (e.g. `English (United States)`)
    * **Play sample** button (▶️)
    * **Pin** icon to favorite a voice

* **Examples by use case**

  Clickable cards for each scenario, for example:

  * **English – Audiobook** (Emotional argument with angry, shouting, and sad styles)
  * **English – Narrator** (Broadcaster introducing a book with a child’s space travel dreams)
  * **English – News** (Weatherman recap in a newscast style)
  * **English – Voice assistant** (Cheerful assistant helping set up a dinner reservation)
  * **Chinese – Audiobook** (Multiple roles with varied emotions)
  * **Chinese – Narrator** (Podcasters commenting on a news article)
  * **Chinese – News** (Casual news reporting voice)
  * **Chinese – Voice assistant** (Call center assistant answering delivery questions)

------------------------- -------------------------

### Custom Voice
*aka "Custom Neural Voice"*

Custom Voice is not available by default; you must complete a form to register for limited access.

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_CustomVoice_RequestAccess.png" width="800" title="Snipped May, 2025" />

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Text to speech** >> **Custom Voice**.

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_CustomVoice.png" width="800" title="Snipped May, 2025" />

Click **+ Create a project**

<!-- ------------------------- -->

###### New Project

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_CustomVoice_NewProject_ProjectType.png" width="800" title="Snipped May, 2025" />

Select **Custom Neural Voice Lite** then click **Next**.

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_CustomVoice_NewProject_Form.png" width="800" title="Snipped May, 2025" />

Complete the form and click **Create**. On the resulting **Select the project you want to work with** screen, click into the new project.

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_CustomVoice_RecordAndBuild.png" width="800" title="Snipped May, 2025" />

Click **Get started** and complete the **Voice talent terms of use** popup form.

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_CustomVoice_NoiseCheck.png" width="800" title="Snipped May, 2025" />

Click the microphone button, wait for assessment, then click **Done**.

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_CustomVoice_RecordingTips.png" width="800" title="Snipped May, 2025" />

Review **Recording tips**, then click **Got it**.

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_CustomVoice_Samples.png" width="800" title="Snipped May, 2025" />

Iteratively run through recording of samples, then click **Train model**.

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_CustomVoice_TrainModel.png" width="800" title="Snipped May, 2025" />

Complete the **Train model** form, then click **Create**. Allow time for processing:

- **Professional Custom Neural Voice**: Training duration varies with data volume but averages **20–40 compute hours** per model ([Microsoft Learn][1])
- **Custom Neural Voice Lite**: Designed for demos and evaluations, takes **less than one compute hour** to train ([Microsoft Learn][2])

[1]: https://learn.microsoft.com/en-us/azure/ai-services/speech-service/professional-voice-train-voice?utm_source=chatgpt.com "Train your professional voice model - Speech service - Azure AI ..."
[2]: https://learn.microsoft.com/en-us/azure/ai-services/speech-service/custom-neural-voice-lite?utm_source=chatgpt.com "Custom neural voice lite - Azure AI services - Learn Microsoft"

When processing is complete, click into the project to review **Sample output**.

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_CustomVoice_SampleOutput.png" width="800" title="Snipped May, 2025" />

------------------------- -------------------------

### Personal Voice

#### Low Code

Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Text to speech** >> **Personal Voice**.

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_PersonalVoice.png" width="800" title="Snipped May, 2025" />

Try sample voices and / or record your own.

<!-- ------------------------- -->

##### Interface Elements

* **Personalization scenarios**: icon list with titles and descriptions

  * **Voice assistant**: "Create a more personalized voice assistant experience…"
  * **Gaming**: "Enable an immersive experience for gamers…"
  * **Language dubbing**: "Expand your global reach and dub your content…"
  * **Entertainment media**: "Create easy-to-use personal voices for stories, audiobooks…"
  * **Accessibility**: "Enable people to build their own voice and use it for natural communications."
  * **Speech translation**: "Allow your meeting participants to be heard in various languages with their true voice."

* **"Try the samples" section**:

  * **Tab selector**: `Scenario-specific` / `Emotional` / `Multi-lingual`
  * **Sample cards**: for each scenario (e.g. Voice assistant, Broadcast, Conversation, Story) showing an illustration and two buttons:

    * **Prompt**: ▶️ plays the original human prompt
    * **Generated**: ▶️ plays the AI-replicated voice

* **"Try your own voice" section**:

  * Instruction text: "Record your voice and create an AI replica in seconds…" with a **this link** to apply for business access
  * **Voice list** pane with a `+ New voice` button (your created voices will appear here)
  * **Detail** pane showing an illustration and a `+ New voice` button when no voices exist

------------------------- -------------------------

### Audio Content Creation

#### Low Code
Navigate to [Azure AI Speech Studio](https://speech.microsoft.com/portal) >> **Text to speech** >> **Audio Content Creation** >> **Discover**.

<!-- ------------------------- -->

##### Discover

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_AudioContentCreation.png" width="800" title="Snipped May, 2025" />

###### News and notes

- **Custom Lexicons**: Speed up your workflow by creating and managing your own word lists for specialized vocabulary
- **Tuning Templates**: Quickly adjust system performance with pre-built templates designed for common scenarios

###### Tutorials

- **How to Create an Azure Account**: Step-by-step video showing the sign-up process, with screenshots and a direct link to watch the tutoria
- **How to Create and Manage Speech Resources**: Guided walkthrough for setting up and managing speech resources in Azure, featuring visuals and a “Watch video” lin
- **How to Add and Manage Users to Use Speech Studio**: Instructions for inviting and managing users, with a tutorial video accessible from the card.
- **Tips for Tuning Operations**: Practical advice for optimizing performance, with an embedded screenshot and a link to view the tips video.

Try each option, then navigate to **My files**.

##### My files

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_AudioContentCreation_MyFiles.png" width="800" title="Snipped May, 2025" />

Click **+ New** and select `Lexicon file` in the resulting menu:

- **Text file**: Create a text file if you want to write scripts, notes, or any general content that will be used later in your Speech Studio project. For example, use this option if you’re preparing the text that will be converted to speech or transcribed
- **Lexicon file**: Create a lexicon if you need to control how Speech Studio pronounces certain words—such as names, technical terms, or brand-specific vocabulary. Use this when you want to ensure your audio output says specialized words correctly

On the resulting **New lexicon** popup, confirm **Language** and **Phonetic alphabet** selections, then click **Create**.

Click **Save** , on the resulting popup, enter name `myLexicon`, and then click **Save**.

Modify the XML as in the following example:

```xml
<?xml version="1.0" encoding="utf-8"?>
<lexicon 
    version="1.0"
    alphabet="ipa"
    xml:lang="en-US"
    xmlns="http://www.w3.org/2005/01/pronunciation-lexicon"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.w3.org/2005/01/pronunciation-lexicon http://www.w3.org/TR/2007/CR-pronunciation-lexicon-20071212/pls.xsd">
  <lexeme>
    <grapheme>BTW</grapheme>
    <alias>By the way</alias>
  </lexeme>
  <lexeme>
    <grapheme>Hello</grapheme>
    <phoneme>hɛ.loˈ</phoneme>
  </lexeme>
  <lexeme>
  <grapheme>Azure</grapheme>
  <phoneme>ˈæʒ.ər</phoneme>
  </lexeme>
</lexicon>
```

> In this example, `Azure` was added to force the correct pronunciation: "AZH-er" instead of "Ah-ZOOR" or "Ah-ZURE"

<img src="..\images\AI_Speech\SpeechStudio_TextToSpeech_AudioContentCreation_MyFiles_NewLexicon.png" width="800" title="Snipped May, 2025" />

Click **Save**.

###### More Samples

- **SQL** (make sure it says "sequel" not "S-Q-L")
- **Contoso** (your fictional company, pronounce as "con-TOE-so")
- **GIF** (choose "jiff" or "giff")
- **Power BI** ("Power B-I" or "Power bee-eye")
- **DataLake** (ensure it’s said as "data lake", not "da-tuh-lake")
- **Nguyen** (common Vietnamese name, set correct phonetics: "win")
- **Route** (pick "root" or "rout" based on preference)
- **Cache** ("cash" not "catch" or "kay-shay")
