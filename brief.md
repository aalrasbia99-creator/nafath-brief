Version: NAFATH-V3
Track: Cybersecurity

## Overview
A trustworthy AI assistant for a government mobile app needs six IT fields to work together. Software engineering uses Semantic Versioning to manage API changes safely and maintain compatibility. AI uses Retrieval-Augmented Generation (RAG) to retrieve relevant information before generating answers. Mobile security protects communication between the app and its services. Networking provides reliable connectivity and supports the growing number of connected devices. Cybersecurity reduces threats such as prompt injection and helps prevent misuse of the assistant. Data management protects citizens' chat logs and personal information. Together, these fields help make the assistant useful, secure, reliable, and respectful of privacy. The project must address prompt injection risks throughout its design and operation.
## Software
Semantic Versioning uses MAJOR.MINOR.PATCH to communicate the impact of API changes. For the assistant’s public API, increase MAJOR when a change breaks backward compatibility. Increase MINOR when adding functionality that remains compatible with existing clients, and increase PATCH for backward-compatible bug fixes. Clear versioning helps mobile apps and other services know whether an update may require changes to their integration.

Resource: Semantic Versioning 2.0.0 - https://semver.org/
## AI
Retrieval-Augmented Generation (RAG) combines a language model with a search or retrieval step. Before answering, the assistant retrieves relevant passages from approved service documents and uses them as context for its response. This can reduce incorrect answers by grounding responses in current, relevant information and making supporting material easier to inspect. RAG does not guarantee accuracy, so the system still needs reliable documents, testing, and monitoring.

Resource: Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks - https://papers.neurips.cc/paper/2020/hash/6b493230205f780e1bc26945df7481e5-Abstract.html
## Mobile
On iOS, App Transport Security (ATS) helps protect privacy and data integrity by requiring secure HTTPS connections that meet Apple's security requirements for standard URL Loading System requests. If the app tries to contact a plain HTTP endpoint, ATS normally blocks the request. Developers should configure the service to use HTTPS rather than weakening ATS, except for carefully justified cases.

Resource: Preventing Insecure Network Connections - https://developer.apple.com/documentation/security/preventing-insecure-network-connections
## Networking
IPv4 uses 32-bit addresses, while IPv6 uses 128-bit addresses, providing a vastly larger address space. IPv6 was designed as a successor to IPv4 and supports a much greater number of addressable devices, which matters as phones, sensors, vehicles, and public-service systems grow. IPv6 also supports simpler address autoconfiguration. Governments need to plan networks so devices and services can communicate across IPv4 and IPv6 environments.

Resource: RFC 8200: Internet Protocol, Version 6 (IPv6) Specification - https://www.rfc-editor.org/rfc/rfc8200
## Cybersecurity
Prompt injection is when input manipulates a large language model (LLM) into ignoring intended instructions or producing unsafe responses. Direct injection comes from a user's prompt; indirect injection is hidden or malicious instructions in material the assistant retrieves, such as a webpage or document. Two mitigations are to treat retrieved content as untrusted and keep it separate from system instructions, and to enforce least-privilege permissions for tools and data. No single defense guarantees prevention.

Resource: LLM01:2025 Prompt Injection - https://genai.owasp.org/llmrisk/llm01-prompt-injection/
## Data
Anonymization irreversibly removes identifying links so a person is no longer reasonably identifiable. Pseudonymization replaces identifiers with codes but allows re-identification using separately held additional information. For chat logs, pseudonymized data generally remains personal data under the GDPR, while truly anonymous information falls outside its scope. The team should remove indirect identifiers as well as names and assess whether re-identification remains reasonably possible.

Resource: Regulation (EU) 2016/679 (GDPR), Recital 26 - https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32016R0679
## Misconception in My Track
A common misconception is that prompt injection only comes from instructions typed directly by a user. In reality, an AI assistant can also receive malicious instructions through external content, such as a webpage or file it retrieves. OWASP states: “Indirect prompt injections occur when an LLM accepts input from external sources, such as websites or files.” This is explained under “Types of Prompt Injection Vulnerabilities,” subsection “Indirect Prompt Injections.” For a government service assistant, retrieved documents should be treated as untrusted, and the model should have only the minimum permissions needed. Testing should include documents as well as chat prompts.
## Open Question
How can the government assistant detect malicious instructions hidden in retrieved service documents without blocking legitimate information citizens need?
