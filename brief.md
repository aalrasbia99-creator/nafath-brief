Version: NAFATH-V3
Track: Cybersecurity

## Overview
A trustworthy AI assistant for a government mobile app needs six IT fields to work together. Software engineering uses Semantic Versioning to manage API changes safely and maintain compatibility. AI uses Retrieval-Augmented Generation (RAG) to retrieve relevant information before generating answers. Mobile security protects communication between the app and its services. Networking provides reliable connectivity and supports the growing number of connected devices. Cybersecurity reduces threats such as prompt injection and helps prevent misuse of the assistant. Data management protects citizens' chat logs and personal information. Together, these fields help make the assistant useful, secure, reliable, and respectful of privacy. The project must consider cybersecurity risks throughout its design and operation.
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

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
