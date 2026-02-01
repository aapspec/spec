# Agent Authorization Profile (AAP)

[![IETF Draft](https://img.shields.io/badge/IETF-draft--aap--oauth--profile-blue)](https://datatracker.ietf.org/doc/draft-aap-oauth-profile/)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)

OAuth 2.0 authorization profile for autonomous AI agents.

## Quick Links

- 📖 [Read Specification](docs/specification/AAP_Complete_Draft_Specification.md)
- 🌐 [Website & Docs](https://aap-protocol.org)
- 🔧 [Reference Implementation](https://github.com/aapspec/reference-impl)
- 📋 [JSON Schemas](https://github.com/aapspec/schemas)
- 🧪 [Test Vectors](https://github.com/aapspec/test-vectors)

## What is AAP?

AAP extends OAuth 2.0 with structured claims for AI agent authorization:

- **Agent Identity**: Explicit, verifiable identity for autonomous agents
- **Capabilities**: Specific actions with enforceable constraints (domains, rate limits, time windows)
- **Task Binding**: Tokens linked to declared purposes
- **Delegation**: Auditable delegation chains between agents and tools
- **Oversight**: Claims indicating actions requiring human approval

## IETF Status

**Current:** Internet-Draft (draft-00)
**Target:** RFC via OAuth Working Group

- [ ] Draft-00 submitted (2025-02-XX)
- [ ] Community feedback period
- [ ] Present at OAuth WG meeting
- [ ] Working Group adoption (target: 2025-Q2)

## Quick Start

```bash
# Install reference implementation
git clone https://github.com/aapspec/reference-impl.git
cd reference-impl
pip install -r requirements.txt

# Generate keys
bash scripts/generate_keys.sh

# Start Authorization Server
cd as && python server.py

# In another terminal, start Resource Server
cd rs && python server.py

# Request token
curl -X POST http://localhost:8080/token \
  -d grant_type=client_credentials \
  -d client_id=agent-01 \
  -d capabilities=search.web
```

## Repository Structure

- `docs/` - Complete specification and guides
- `draft/` - IETF Internet-Draft (XML format)
- `examples/` - Example use cases and integrations

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Community

- **IETF Mailing List:** oauth@ietf.org
- **GitHub Discussions:** [github.com/aapspec/spec/discussions](https://github.com/aapspec/spec/discussions)
- **Website:** https://aap-protocol.org

## License

Apache License 2.0 - See [LICENSE](LICENSE)

