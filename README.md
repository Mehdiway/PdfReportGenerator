# HtmlToPdf - Invoice PDF Generator

HtmlToPdf is a .NET 9 Web API that generates professional invoice PDFs from HTML templates using Handlebars and PuppeteerSharp. It provides a ready-to-use endpoint for generating sample invoices with realistic data, making it ideal for reporting, invoicing, or document automation scenarios.

## Features

- **REST API** for generating invoice PDFs on demand
- **Handlebars** templating for customizable invoice layouts
- **PuppeteerSharp** for high-fidelity PDF rendering (headless Chromium)
- **Swagger UI** for easy API exploration
- **Sample data** generation using Bogus
- **Multiple templates** (modern and simple)

## Getting Started

### Prerequisites

- [.NET 9 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/9.0)
- Internet access (for PuppeteerSharp to download Chromium on first run)

### Setup

1. **Clone the repository**
   ```sh
   git clone <your-repo-url>
   cd PdfGenerator/after/PdfReporting/HtmlToPdf
   ```
2. **Restore dependencies**
   ```sh
   dotnet restore
   ```
3. **Run the application**

   ```sh
   dotnet run
   ```

   The API will start (by default on `https://localhost:7138` and `http://localhost:5010`).

4. **Explore the API**
   Open [https://localhost:7138/swagger](https://localhost:7138/swagger) in your browser to view and test the API endpoints.

## Usage

### Generate an Invoice PDF

- **Endpoint:** `GET /invoice-report`
- **Description:** Returns a generated invoice as a PDF file with sample data.
- **Response:** `application/pdf` (downloadable invoice)

#### Example (using `curl`):

```sh
curl -k https://localhost:7138/invoice-report --output invoice.pdf
```

### Customization

- **Templates:**
  - `Views/InvoiceReport.hbs` (modern, styled)
  - `Views/SimpleTemplate.hbs` (minimal)
- **Logo:** Place your logo in `logo.png` (used in the PDF header)
- **Data Model:** See `Contracts/Invoice.cs`, `Address.cs`, and `LineItem.cs` for structure.

## Project Structure

```
PdfReporting/HtmlToPdf/
├── Contracts/           # Data models (Invoice, Address, LineItem)
├── Views/               # Handlebars templates for invoices
├── logo.png             # Logo used in PDF
├── InvoiceFactory.cs    # Generates sample invoice data
├── Program.cs           # Main API logic
├── appsettings.json     # Configuration
├── HtmlToPdf.csproj     # Project file
```

## Dependencies

- [PuppeteerSharp](https://github.com/hardkoded/puppeteer-sharp) - Headless Chromium for PDF rendering
- [Handlebars.Net](https://github.com/Handlebars-Net/Handlebars.Net) - Templating engine
- [Bogus](https://github.com/bchavez/Bogus) - Fake data generator
- [Swashbuckle.AspNetCore](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) - Swagger/OpenAPI

## License

This project is licensed under the MIT License. See [LICENSE](../LICENSE) for details.

## Author

- [Your Name](mailto:your.email@example.com)
