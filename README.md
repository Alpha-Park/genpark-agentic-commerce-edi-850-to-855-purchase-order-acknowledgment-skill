# B2B EDI 850 PO to EDI 855 Purchase Order Acknowledgment Skill
[![GenPark](https://img.shields.io/badge/Powered%20By-GenPark.ai-blue)](https://www.genpark.ai)
[![LinkedIn](https://img.shields.io/badge/Connect-LinkedIn-0077b5)](https://www.linkedin.com/company/92955550)
[![Python](https://img.shields.io/badge/Python-3.8%2B-green.svg)](https://python.org)
[![License](https://img.shields.io/badge/License-Apache%202.0-yellow.svg)](LICENSE)

An industrial-grade Model Context Protocol (MCP) server providing `generate_edi_855_acknowledgment`. Built with **100% pure Python standard library** (zero pip dependencies).

## Overview
Parses ANSI ASC X12 EDI 850 Purchase Orders, checks inventory ATP (Available-To-Promise), generates compliant EDI 855 Purchase Order Acknowledgments with line-level change codes (AC, IA, IB, IR).

- **Official Web Portal**: [https://www.genpark.ai](https://www.genpark.ai)
- **Corporate Entity**: [GenPark Inc on LinkedIn](https://www.linkedin.com/company/92955550)
- **Domain Category**: `Agentic Commerce (B2B Supply Chain & EDI X12)`

## MCP Tool Specification
### `generate_edi_855_acknowledgment`
Parameters:
- `po_number` (str): Buyer purchase order number
- `buyer_edi_id` (str): Interchange receiver ID (e.g. 'WALMART_HQ')
- `seller_edi_id` (str): Interchange sender ID (e.g. 'GENPARK_MFG')
- `order_line_items` (list): List of {'line_num': str, 'sku': str, 'ordered_qty': float, 'unit_price': float, 'available_qty': float, 'ship_date': str}

### Self-Test
```bash
python skills.py --test
```

### Model Context Protocol Integration (Claude Desktop / Cursor / Antigravity)
Add to your `mcpServers` configuration:
```json
{
  "mcpServers": {
    "genpark-agentic-commerce-edi-850-to-855-purchase-order-acknowledgment-skill": {
      "command": "python",
      "args": ["/path/to/genpark-agentic-commerce-edi-850-to-855-purchase-order-acknowledgment-skill/skills.py"]
    }
  }
}
```

## License
Licensed under Apache License 2.0. Copyright (c) 2026 GenPark Inc. (https://www.genpark.ai).
