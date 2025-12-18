# Internet-Draft: Cross-Domain AuthZ Information Sharing for Agents

## Overview

This repository contains an Internet-Draft proposing a novel approach for sharing authorization information across administrative domains in distributed multi-agent systems. The draft addresses challenges when AI agents and Model Context Protocol (MCP) servers operate across different Identity Providers and Authorization Servers.

## Document Information

- **Draft Name**: `draft-ietf-oauth-cross-domain-authz-information-sharing-for-agents-00`
- **Category**: Informational
- **Workgroup**: OAuth (proposed)
- **Status**: Individual Draft (Version 00)

## Key Innovation

The draft proposes extending OAuth 2.0 Client-ID Metadata with W3C Verifiable Credentials (VC) to enable:

- **Dynamic agent/server identity** across domains
- **Flexible, extensible claims** beyond standard OAuth parameters
- **Privacy-preserving authorization** via selective disclosure
- **Cryptographically verifiable** trust assertions
- **Compliance-ready** audit trails

## Repository Contents

- `draft-ietf-oauth-cross-domain-authz-information-sharing-for-agents-00.xml` - Main Internet-Draft source (XML RFC format)
- `README.md` - This file + detailed technical analysis

## Generating PDF/HTML/TXT Output

### Prerequisites

Install the required tools:

```bash
# Install xml2rfc (Python package)
pip install xml2rfc

# On macOS with Homebrew:
brew install xml2rfc

# On Debian/Ubuntu:
apt-get install xml2rfc
```

### Generate Output Formats

From the directory containing the XML file:

```bash
# Generate text format (required for IETF submission)
xml2rfc draft-ietf-oauth-cross-domain-authz-information-sharing-for-agents-00.xml --text

# Generate HTML (for web viewing)
xml2rfc draft-ietf-oauth-cross-domain-authz-information-sharing-for-agents-00.xml --html

# Generate PDF (requires additional dependencies)
xml2rfc draft-ietf-oauth-cross-domain-authz-information-sharing-for-agents-00.xml --pdf

# Generate all formats at once
xml2rfc draft-ietf-oauth-cross-domain-authz-information-sharing-for-agents-00.xml --text --html --pdf
```

### Alternative: Using Docker

If you prefer not to install tools locally:

```bash
# Using the official IETF tools container
docker run -v $(pwd):/rfc paulej/rfctools xml2rfc \
  /rfc/draft-ietf-oauth-cross-domain-authz-information-sharing-for-agents-00.xml \
  --text --html --pdf
```

### Validation

Validate the XML before generating outputs:

```bash
# Check for XML syntax and structure issues
xml2rfc draft-ietf-oauth-cross-domain-authz-information-sharing-for-agents-00.xml --validate
```

## Quick Start for Reviewers

1. **Clone this repository**

   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Generate readable format**

   ```bash
   xml2rfc draft-ietf-oauth-cross-domain-authz-information-sharing-for-agents-00.xml --html
   ```

3. **Open in browser**
   ```bash
   open draft-ietf-oauth-cross-domain-authz-information-sharing-for-agents-00.html
   ```

## Document Structure

1. **Introduction** - Problem statement for cross-domain agent authorization
2. **Definitions** - Key terms (Agent, MCP Server, AS, IdP, Claims, Domain)
3. **Problem Statement** - Architecture and challenges visualization
4. **Use Cases** - Predictive threat detection, automated compliance
5. **Requirements** - 6 core requirements for solutions
6. **Solution Analysis** - Comparison of 4 approaches:
   - RFC 7591 Dynamic Client Registration
   - SCIM Extensions
   - Client-ID Metadata
   - **Client-ID Metadata + W3C VC** (proposed)
7. **Examples** - Concrete metadata and VC examples
8. **IANA/Security Considerations**

## Known Issues (Version 00)

⚠️ **This is an early draft with known gaps** (see detailed analysis in README.md):

### Critical

- [ ] Document naming inconsistency (`draft-vc-client-id-metadata-00` vs intended name)
- [ ] Missing formal `vc+jwt` claim specification
- [ ] Incomplete security threat model
- [ ] No DID resolution requirements

### Important

- [ ] Missing error response formats
- [ ] No AS discovery mechanism defined
- [ ] IANA registration needed for new parameters
- [ ] Examples contain typos (XYZ vs XYX)

### Editorial

- [ ] Missing RFC 2119 boilerplate for normative keywords
- [ ] Inconsistent MCP terminology usage
- [ ] Incomplete reference list (missing DID-CORE, StatusList2021)

## Contributing

This is an individual Internet-Draft. Feedback is welcome via:

- **GitHub Issues**: For technical discussion and suggestions
- **Email**: Contact authors directly (see XML for addresses)
- **IETF OAuth WG**: For formal working group feedback

### Providing Feedback

When submitting feedback, please:

1. Reference specific section numbers
2. Provide concrete suggested text where possible
3. Identify whether issue is editorial or technical
4. Consider requirements impact (see Section 5)

## Technical Analysis

A comprehensive technical analysis is included in this README, covering:

- **Strengths**: Problem clarity, systematic comparison, innovative approach
- **Critical Issues**: 7 major technical gaps
- **Recommendations**: Specific fixes and enhancements
- **Priority Actions**: High/Medium/Low categorization

See full analysis above for details.

## Authors

- Jean Diaconu (jdiaconu@cisco.com)
- Marcelo Yannuzzi (mayannuz@cisco.com)
- Herve Muyal (hmuyal@cisco.com)
- Frank Brockners (fbrockne@cisco.com)

## Related Standards

- [RFC 7591](https://www.rfc-editor.org/rfc/rfc7591) - OAuth 2.0 Dynamic Client Registration
- [W3C VCDM 2.0](https://www.w3.org/TR/vc-data-model-2.0/) - Verifiable Credentials Data Model
- [OAuth Client-ID Metadata](https://datatracker.ietf.org/doc/draft-ietf-oauth-client-id-metadata-document/) - OAuth 2.0 Client Identity Metadata Document
- [SCIM Agent Extensions](https://datatracker.ietf.org/doc/draft-abbey-scim-agent-extension/) - SCIM Extensions for Agents

## License

IETF Trust Legal Provisions (TLP 5.0) - See document header

## Version History

- **00** (2025-01) - Initial individual draft submission

---

**Note to Implementers**: This is a work-in-progress draft. Do not implement for production use without coordination with the authors. Several critical specifications are incomplete and subject to change.
