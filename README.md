<p align="center">
  <img src="assets/logo.jpg" alt="openMAG logo" />
</p>

<br />
<br />

The openMAG Project is an open-source, community-driven educational project focused on understanding cinema camera SSD media,
with an emphasis on REDMAG and MINIMAG, and documenting the concepts and validation workflows involved.

This repository is educational and research oriented. It is not affiliated with or endorsed by RED Digital Cinema.

## Why openMAG Project Exists

Many cinema cameras rely on approved, proprietary media. Over time, that media becomes harder to replace, more expensive,
or simply unavailable. When original SSD-based media starts to fail, creators can be left with fewer options:
pay escalating prices for aging stock, risk unreliable used media, or retire otherwise functional cameras.

The openMAG Project exists to preserve long-term usability of supported camera platforms by documenting how media works at a technical level,
and by sharing research that helps the community understand:

- how SSDs identify themselves and report capabilities
- how camera media validation commonly works (at a conceptual level)
- how to test, verify, and document outcomes safely and responsibly

This follows the spirit of other preservation-minded open projects that keep valuable hardware viable through time:
projects that reverse-engineer interfaces, publish compatibility knowledge, and build community-maintained documentation.
openMAG applies that same mindset to cinema SSD media—education first, evidence driven, and open to peer review.

## Who we are

The openMAG Project is built by a community of filmmakers, engineers, and hardware enthusiasts who care about:
- extending the useful life of professional tools
- reducing single-vendor dependency through knowledge and documentation
- sharing research openly so others can learn and contribute

If you have logs, photos, test results, controller/NAND identification, or documentation improvements, you can help.

## What this project is (and is not)

**This project is:**
- a learning resource and technical reference
- a documentation hub for SSD/media concepts and validation behavior
- a community space for collecting repeatable test results and troubleshooting

**This project is not:**
- a commercial product or service
- endorsed by, affiliated with, or supported by RED Digital Cinema
- a guarantee that any specific SSD will work in any specific camera
- a place to share proprietary binaries, leaked tools, or NDA-protected materials

## Safety and responsibility

Working with SSD firmware, low-level identifiers, adapters, and camera media can cause:
- permanent SSD failure (“bricking”)
- loss or corruption of footage
- camera instability
- voided warranties

You are responsible for your equipment, your data, and compliance with all applicable laws.
Read the disclosures in `legal/` before attempting experiments.

## Projects

- [REDMAG](docs/redmag/README.md)
- [MINIMAG](docs/minimag/README.md)


## Repository structure (high level)

- `docs/` — the educational content and guided learning paths  
- `legal/` — disclosures, trademarks, and liability limitations  
- `assets/` — images and diagrams (including the logo)

## Contributing

This project improves when the community contributes real-world findings and better explanations.

See `CONTRIBUTING.md` for:
- how to propose documentation edits
- how to submit test results (with enough detail to reproduce)
- what types of contributions are not accepted (for legal/safety reasons)

If you are new to contributing on GitHub, start small:
- fix wording or clarify a paragraph
- add a troubleshooting case and what resolved it
- add a reference link to a public datasheet or standard

## Legal and disclosures

Open-source documentation does not remove risk. The legal files exist to protect contributors and users,
and to keep the project grounded in educational intent.

- `legal/DISCLAIMER.md` — educational use and risk disclosure  
- `legal/LIABILITY.md` — limitation of liability  
- `legal/TRADEMARKS.md` — trademark attribution and non-affiliation statement  
- `legal/EDUCATIONAL_USE.md` — intent and scope of the project  

If you contribute, you agree to follow these guidelines and keep content educational and lawful.

## License and attribution

This repository is open licensed to encourage collaboration and reuse.

- See `LICENSE` for the license text.
- See `NOTICE` for attribution guidance.

If you fork or reuse this work, please keep a visible reference to:
**“openMAG – Open Source Cinema SSD Project”**

That attribution helps the community find improvements and keeps the ecosystem connected.

## Contact and community

For now, use GitHub Issues and Pull Requests:
- Issues: questions, doc improvements, research notes
- Pull requests: proposed changes with clear reasoning and evidence when applicable

## TL;DR: Upgrading REDMAGs with Custom SSDs

### Key Points
- **REDMAG** firmware only checks: (1) SSD model number and (2) reported capacity
- Maximum capacity: **512GB** (hardcoded whitelist limitation)
- Model number must match [approved whitelist](https://github.com/openmag-project/openmag/blob/main/docs/redmag/whitelist-overview.md)
- Capacity must exactly match what's embedded in the model number (e.g., *RED 512GB V4*)
- No `0x90h` value concerns like with MINIMAG

### Modifying SSD Identity
**The Challenge:** Changing model number and capacity requires professional tools or **MP Tools (Mass Production Tools)**

**MP Tool Requirements:**
- Windows-only
- Will trigger antivirus false positives (normal behavior)
- Must match your specific SSD controller and NAND chips
- Usually found on foreign websites (Chinese/Russian forums)
- Recommended source: [https://www.usbdev.ru/files/#gsc.tab=0](https://www.usbdev.ru/files/#gsc.tab=0)

### SSD Selection Tips
**Controllers:** SSDs with **SMI (Silicon Motion)** controllers are easier—leaked MP Tools more available. Avoid major brands (Toshiba, Samsung) as MP Tools are rarely leaked.

**Form Factors Tested:** M.2 SATA, mSATA, microSATA, 2.5" SSDs all work (camera reads SATA data)

**Best Choice:** **mSATA-based REDMAGs** are easiest to work with

**Avoid:** microSATA (discontinued, requires unreliable adapters with voltage/grounding issues)

**Specifications:** DRAM-based SSDs preferred over DRAM-less for cinema use

**Power Note:** 2.5" SSDs need external 5V power (camera only handles data connection)—not practical outside testing

### Cost Reference
- **64GB REDMAG** → **512GB upgrade**: ~$70/REDMAG + ~$100/SSD

### openMAG Project
**GitHub:** [https://github.com/openmag-project/openmag/tree/main](https://github.com/openmag-project/openmag/tree/main)

**Goals:**
- Educational documentation for REDMAG and MINIMAG modifications
- Free 3D-printable shells for mSATA/M.2 SATA drives
- Custom PCB pass-through boards (only paid component—minimal cost)
- Upcoming YouTube tutorial

### Next Steps
1. Research MP Tools on YouTube to understand SSD compatibility
2. Identify your SSD controller and NAND chips before purchasing
3. Use AI tools (ChatGPT, Claude) to help throughout the process
4. Check the openMAG GitHub for detailed documentation