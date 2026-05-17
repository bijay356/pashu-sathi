# Pashu Sathi (पशु साथी)

Offline Nepali veterinary AI assistant for rural livestock farmers, powered by Gemma 4 and Ollama.

Pashu Sathi helps farmers describe livestock symptoms in simple Nepali and receive safe first-aid guidance, urgency levels, and veterinarian referral advice. It is designed for villages where internet access is unreliable and licensed veterinary support is not always immediately available.

## Why It Matters

Nepal has millions of livestock farmers, but many rural communities have limited access to timely veterinary advice. A sick buffalo, cow, goat, calf, or poultry flock can create a major financial loss for a family.

Pashu Sathi is built to be:

- Offline-first: runs locally after setup
- Nepali-first: responds in Devanagari Nepali
- Safety-first: does not prescribe drug names, brands, or doses
- Vet-bridging: guides farmers toward licensed veterinary care

## Technology

- Model: Gemma 4 via Ollama
- Custom model name: `pashu`
- Interface/demo: `index.html`
- Deployment target: basic Windows laptop, no GPU required
- Language: Nepali Devanagari

## Covered Conditions

1. Mastitis / थन सुन्निने
2. Foot and Mouth Disease / खोरेत
3. Bloat / पेट फुल्ने
4. Milk Fever / दूध ज्वरो
5. Calf Diarrhea / बाच्छाको झाडापखाला
6. Internal Parasites / आन्द्राको जुका
7. Retained Placenta / साल नझर्ने
8. PPR / बाख्राको प्लेग
9. Newcastle Disease / राणीखेत
10. Heat Stress / गर्मीको असर

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

Example query:

```text
मेरो भैंसीको थन सुन्निएको छ, दूधमा रगत आएको छ। के गर्ने?
```

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
├── README.md
├── LICENSE
├── Modelfile
├── index.html
├── docs/
│   ├── pashu_sathi_prompt.txt
│   └── pashu_sathi_knowledge.docx
└── demo/
    ├── screenshots/
    └── video/
        └── README.md
```

## Author

Bijay Kumar Mandal  
Licensed Veterinary Officer, Nepal

## License

This project is released under the Creative Commons Attribution 4.0 International License.
