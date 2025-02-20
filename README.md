# LLM-Powered Email Classification and Order Processing

## Overview
This project is a proof-of-concept application that leverages Large Language Models (LLMs) to classify customer emails and process orders, improving operational efficiency for a fashion retail store. The system automates email categorization, order fulfillment, and customer responses, reducing manual effort and enhancing the customer experience.

## Objective
The goal is to build an AI-powered solution that intelligently processes email order requests and customer inquiries. The system will:
- Categorize emails into **product inquiries** or **order requests**.
- Process orders based on stock availability.
- Generate appropriate responses for each scenario.

## Data Sources
The system interacts with a Google Spreadsheet containing:
- **Product Catalog**: A list of products with details like product ID, name, category, stock availability, description, and season.
- **Customer Emails**: A dataset of incoming emails with unique email IDs, subject lines, and message bodies.

## Key Features
### 1. Email Classification
- Uses LLMs to classify each email as either a **product inquiry** or an **order request**.
- Outputs are saved in the **email-classification** sheet.

#### Example Output:
| Email ID | Category          |
|----------|------------------|
| 101      | Product Inquiry  |
| 102      | Order Request    |

### 2. Order Processing
- Verifies product availability for order requests.
- If in stock, the order is **created** and inventory is updated.
- If out of stock, the status is marked as **out of stock**.
- Results are stored in the **order-status** sheet.

#### Example Output:
| Email ID | Product ID | Quantity | Status       |
|----------|------------|---------|-------------|
| 102      | P001       | 2       | Created     |
| 103      | P005       | 1       | Out of Stock |

### 3. Order Response Generation
- Generates email responses based on the order processing results.
- If an order is fulfilled, a confirmation email is sent.
- If an order is out of stock, an alternative solution is suggested.
- Responses are stored in the **order-response** sheet.

#### Example Output:
| Email ID | Response |
|----------|----------|
| 102      | Your order for 2 units of P001 has been processed successfully. |
| 103      | Unfortunately, P005 is out of stock. Please consider an alternative. |

### 4. Handling Product Inquiries
- Uses LLMs to answer customer queries based on the product catalog.
- Ensures scalability to handle large datasets without exceeding token limits.
- Stores responses in the **inquiry-response** sheet.

#### Example Output:
| Email ID | Response |
|----------|----------|
| 101      | The P002 is a summer collection dress available in multiple sizes. |

## Implementation Details
- Uses **GPT-4o** via OpenAI API for email processing and response generation.
- Employs **LangChain** and other Python libraries for optimized AI-driven workflows.
- Handles large datasets efficiently by minimizing unnecessary API calls.

## Evaluation Criteria
- **Effective AI Utilization**: Proper use of LLMs to categorize emails and generate responses.
- **Code Quality & Completeness**: Ensures well-structured, maintainable, and functional code.
- **Output Accuracy**: Ensures correctness and proper formatting of stored results.
- **Scalability**: Handles a catalog of over 100,000 products efficiently.

## Getting Started
1. Set up API keys for OpenAI.
2. Load the Google Spreadsheet containing product and email data.
3. Run the script to classify emails, process orders, and generate responses.
4. Verify the results in their respective sheets.

## Dependencies
- Python 3.x
- OpenAI API
- LangChain
- Pandas
- Google Sheets API

## Conclusion
This project demonstrates how AI can automate email classification, order processing, and customer communication for a retail business. By integrating LLMs, we streamline operations, improve efficiency, and enhance customer satisfaction.

