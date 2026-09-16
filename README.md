# suyu Legal Notice

**Version:** 1.2  
**Last updated:** September 16, 2026  

---

## 1. Purpose

This document sets out the legal position of the suyu emulator. It explains why the software is lawful under United States copyright law, why common claims made against it in DMCA notices are incorrect, and what users may and may not do with it.

It is written for placement in the project’s public repositories. It is not legal advice. Copyright and anti-circumvention rules differ by country; readers outside the United States should check the law that applies to them.

---

## 2. What suyu Is

suyu is a free, open-source emulator for the Nintendo Switch. It re-implements the behaviour of the Switch’s hardware and operating system (Horizon OS) in software so that Switch games and homebrew can run on other platforms—primarily Windows, Linux and Android.

The code is written in C++ and released under the **GNU General Public License version 3 or later (GPL-3.0-or-later)**. The full source is available in the project’s public repositories. The license permits anyone to copy, modify and redistribute the software, provided they follow the terms of the GPL. It also makes clear that the authors accept no liability for how the software is used (GPL-3.0 §§ 15 and 16).

suyu does **not** contain any proprietary Nintendo code, Nintendo’s cryptographic keys, Nintendo firmware images, or any game data. Those materials must be supplied by the user.

---

## 3. Core Legal Position

### 3.1 No circumvention of technological protection measures

Nintendo protects its Switch games with encryption. The games cannot be read until they are decrypted with certain cryptographic keys (commonly called `prod.keys` and related title keys). Nintendo treats this encryption as a “technological protection measure” (TPM) under the Digital Millennium Copyright Act.

suyu does not break or bypass that encryption on its own. It expects the user to provide:

- a dump of a game the user has lawfully obtained, and  
- the cryptographic keys obtained from a Switch console the user owns.

Only then does suyu apply a standard, publicly documented algorithm—AES in the modes defined by the U.S. National Institute of Standards and Technology—to decrypt the data the user already possesses. Because both the keys and the game data come from the user, the software itself does not “circumvent a technological measure” within the meaning of 17 U.S.C. § 1201(a)(3).

### 3.2 Interoperability reverse engineering is protected

Section 1201(f) of the DMCA contains an explicit exemption for reverse engineering performed to achieve interoperability between independently created computer programs. suyu exists to make Horizon OS software able to run on ordinary PCs and phones. That is a classic interoperability purpose. The exemption is not unlimited, but the design of suyu—user-supplied keys, no distribution of Nintendo code, no commercial trafficking in keys—fits inside the protection Congress wrote into the statute.

### 3.3 Emulation itself is not illegal

U.S. courts and decades of industry practice have accepted that writing software that mimics the behaviour of a game console is lawful, provided the emulator does not copy protected code or data belonging to the console manufacturer. The same principle that allows other console emulators to exist also applies here.

---

## 4. Project Rules

These rules are part of how the project is designed and operated:

1. **Piracy is not supported or condoned.**  
   The project will never distribute, link to, or help users obtain copyrighted games, keys or firmware.

2. **Keys and firmware must come from the user.**  
   suyu will not generate, ship or automatically download Nintendo’s cryptographic keys or system firmware. The user must dump them from hardware they own.

3. **Games must be lawfully obtained.**  
   The only games a user is entitled to load are those they have purchased and dumped themselves, or otherwise acquired through a channel that does not infringe copyright.

4. **No commercial exploitation.**  
   The project does not accept donations, sell builds, or run any form of monetisation tied to the emulator.

5. **Source availability.**  
   Because the software is under the GPL, the complete corresponding source code is published. Anyone can inspect it and verify that it contains no proprietary Nintendo material.

These choices distinguish suyu from software that ships keys, generates keys from proprietary material, or is structured to make the acquisition of unauthorised copies easy.

---

## 5. Response to Common DMCA Claims

Nintendo and parties acting on its behalf have filed multiple DMCA notices against repositories that host suyu. The notices tend to follow a standard pattern. Each main claim is addressed below.

### 5.1 “The emulator is primarily designed to circumvent Nintendo’s TPMs”

This tracks the language of 17 U.S.C. § 1201(a)(2), which prohibits trafficking in technology “primarily designed or produced for the purpose of circumventing a technological measure.”

The claim mischaracterises what the software does. suyu is designed to emulate the Switch so that a user who already has lawful copies of games and the corresponding keys can run those games on other hardware. The decryption step is not the purpose of the program; it is a necessary intermediate step that occurs only after the user has supplied both the encrypted data and the keys.

A tool that requires the user to bring their own keys and their own lawfully obtained games is not “primarily designed” to circumvent anything. It is designed to provide interoperability. The statutory text and the legislative history of § 1201(f) recognise this distinction.

### 5.2 “The emulator necessarily uses unauthorised copies of cryptographic keys”

The keys are not supplied by suyu. They are supplied by the user. When a person dumps the keys from a Switch console they own, those keys are not “unauthorised” in that person’s hands for the purpose of playing games they also own.

The notice language treats every use of the keys outside Nintendo’s own hardware as automatically unauthorised. That reading collapses the distinction between a user exercising rights over material they already possess and a third party distributing keys or facilitating mass unauthorised access. suyu performs only the first function.

### 5.3 “The emulator decrypts unauthorised copies of games”

The games are not supplied by the project. If a user loads a dump they obtained unlawfully, that is the user’s infringement, not the emulator’s. The software is structured so that it cannot run commercial titles without the user first providing both the dump and the keys. Responsibility for the legality of those materials rests with the person who supplies them.

### 5.4 “The work is not licensed under an open-source license”

This statement appears in at least one published Nintendo notice directed at suyu repositories. It is false.

The repositories carry the GPL-3.0 license file. The source code is publicly available under that license. Stating under penalty of perjury that the software is not open-source, when the license and the source are in plain view, is a material misrepresentation of fact.

### 5.5 Liability for knowing misrepresentation (§ 512(f))

Section 512(f) provides that any person who knowingly materially misrepresents that material is infringing is liable for damages, including costs and attorneys’ fees, incurred by the alleged infringer as a result of the service provider’s reliance on the misrepresentation.

A notice that ignores the user-supplied-key design, ignores the interoperability exemption in § 1201(f), asserts that GPL-licensed source is “not open-source,” and treats every emulator capable of decryption as *per se* trafficking raises precisely the kind of knowing misrepresentation § 512(f) was written to deter. Whether any particular notice meets the “knowingly” threshold is a question for a court, but the factual inaccuracies are clear on the face of the documents.

---

## 6. Relationship to the Yuzu / Tropic Haze Litigation

In 2024 Nintendo sued Tropic Haze LLC, the company behind the Yuzu emulator, and obtained a settlement and permanent injunction. Notices filed against later projects frequently cite that case as if it automatically renders every subsequent Switch emulator illegal.

It does not.

The injunction binds the named parties and those acting in active concert with them. It does not rewrite the DMCA or convert the act of writing an emulator that requires user-supplied keys into a strict-liability offence. suyu was designed to avoid the specific practices Nintendo highlighted in that litigation—particularly automatic key generation and commercial monetisation. The legal analysis must rest on the actual design of suyu and on the text of the statute, not on the existence of a settlement between other parties.

---

## 7. What Users May and May Not Do

**Users may:**

- Download and run the suyu binaries or build from source.  
- Dump keys and firmware from a Switch console they own.  
- Dump games they have lawfully purchased.  
- Use those materials with suyu for personal interoperability purposes.  
- Modify the source code under the terms of the GPL.

**Users may not:**

- Distribute copyrighted game dumps, keys or firmware.  
- Ask the project or its community for copyrighted material.  
- Use suyu to play games they do not own.  
- Claim that the project endorses or facilitates piracy.

The project’s community rules exist to enforce the second list. Violations result in removal from official channels.

---

## 8. Practical Realities

A well-founded legal position does not prevent a large rights-holder from sending DMCA notices. Hosting platforms often process notices quickly and with limited review. Temporary takedowns can and do occur.

The project’s response is:

- to keep the complete source available under the GPL on platforms that will host it,  
- to maintain a clear public record of the legal position set out in this document, and  
- to evaluate counter-notice and § 512(f) options on a case-by-case basis when resources and facts justify doing so.

No representation is made that every platform will always accept the analysis above. The analysis is offered because it is correct, not because it guarantees frictionless hosting.

---

## 9. Summary

suyu is an open-source emulator released under the GPL-3.0. It contains no Nintendo code, keys or game data. It requires the user to supply lawfully obtained keys and game dumps. Its purpose is interoperability reverse engineering of the kind Congress protected in DMCA § 1201(f).

Claims that the software is primarily designed to circumvent technological protection measures, that it necessarily uses unauthorised keys, or that it is not open-source, do not survive contact with the actual design of the program or the text of the statute.

The emulator is legal. Piracy is not. The project does not enable, support or excuse the latter.

---

## 10. Document Control

This notice may be reproduced in full in any repository or website that hosts suyu, provided the text is not altered in a way that changes its meaning.

Questions about the legal position should be directed through the project’s official public channels. No individual contributor is authorised to give private legal advice on behalf of the project.

**End of notice.**
