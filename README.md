# Pashu Sathi

Offline Nepali veterinary AI assistant for rural livestock farmers, powered by Gemma 4 and Ollama.

Pashu Sathi helps farmers describe livestock symptoms in simple Nepali and receive safe first-aid guidance, urgency levels, and veterinarian referral advice. It is designed for villages where internet access is unreliable and licensed veterinary support is not always immediately available.

## Why It Matters

Nepal has millions of livestock farmers, but many rural communities have limited access to timely veterinary advice. A sick buffalo, cow, goat, calf, or poultry flock can create a major financial loss for a family.

Pashu Sathi is built to be:

- Offline-first: runs locally after setup
- Nepali-first: responds in Devanagari Nepali
- Safety-first: does not prescribe drug names, brands, or doses
- Voice-friendly: farmers with limited literacy can speak their problem instead of typing
- Vet-bridging: guides farmers toward licensed veterinary care

## Key Features

- Nepali Devanagari veterinary guidance
- Voice input button for farmers who cannot easily read or type
- Text-to-speech answer playback
- Local Ollama connection to the custom `pashu` model
- Demo screenshots for 10 critical livestock conditions
- Conservative safety policy with veterinarian referral

## Technology

- Model: Gemma 4 via Ollama
- Custom model name: `pashu`
- Interface/demo: `index.html`
- Deployment target: basic Windows laptop, no GPU required
- Language: Nepali Devanagari

## Covered Conditions

1. Mastitis
2. Foot and Mouth Disease
3. Bloat
4. Milk Fever
5. Calf Diarrhea
6. Internal Parasites
7. Retained Placenta
8. PPR
9. Newcastle Disease
10. Heat Stress

## Run Locally

Install Ollama, then pull Gemma 4:

```bash
ollama pull gemma4
```

Create the custom Pashu Sathi model:

```bash
ollama create pashu -f Modelfile
```

Run the assistant:

```bash
ollama run pashu
```

Open `index.html` in a browser on the same laptop. The page calls the local Ollama server at:

```text
http://127.0.0.1:11434
```

Example query:

```text
मेरो भैंसीको थन सुन्निएको छ, दूधमा रगत आएको छ। के गर्ने?
```

## Voice Mode

The demo page includes a microphone button so farmers can speak their problem. Browser speech recognition support depends on the browser and device. If speech recognition is unavailable, the text mode remains available.

The answer can also be read aloud with the speaker button. This supports farmers who are less comfortable reading long text.

## Safety Policy

Pashu Sathi is not a replacement for a licensed veterinarian.

It does not provide:

- Specific drug names
- Brand names
- Doses such as ml, tablets, or mg/kg
- Final diagnosis without veterinary examination

It does provide:

- Urgency level
- Possible condition
- First-aid steps
- What not to do
- Red flags
- Recommendation to contact a local veterinarian

## Repository Structure

```text
pashu-sathi/
|-- README.md
|-- LICENSE
|-- Modelfile
|-- index.html
|-- docs/
|   |-- pashu_sathi_prompt.txt
|   `-- pashu_sathi_knowledge.docx
`-- demo/
    |-- queries.md
    |-- screenshots/
    `-- video/
        `-- README.md
```

## Author

Bijay Kumar Mandal  
Licensed Veterinary Officer, Nepal

## License

This project is released under the Creative Commons Attribution 4.0 International License.
