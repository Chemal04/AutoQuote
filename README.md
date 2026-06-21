# AutoQuote
Mechanic shop billier
# ShopFlow — Auto Repair Estimate & Workflow Tool

> A smart repair workflow tool for independent auto mechanics and small shop owners who need to quickly generate professional service estimates and repair orders — without the paperwork slowdown.

***

## What It Does

ShopFlow lets a mechanic select a vehicle, choose a service type, and instantly generate a formatted, customer-ready repair order. Key features include:

- **Vehicle selector** — year, make, and model lookup
- **Service search** — auto-fills estimated labor time and suggested parts cost range
- **Diagnostic Fee toggle** — line-items a flat diagnostic charge when enabled
- **Customer Approval Status** — track Pending / Approved / Declined without leaving the screen
- **Live Repair Order preview** — right-panel output updates in real time
- **Job Summary Box** — one-click copyable plain-English sentence ready to text or email the customer
- **Labor markup controls** — adjustable markup with inline tooltip guidance
- **Dark-surface UI** — charcoal + teal theme designed for shop floor readability

***

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript (no build step) |
| Fonts | Fontshare (Satoshi) via CDN |
| Icons | Lucide Icons via CDN |
| Styling | Custom CSS with design tokens (OKLCH color system) |
| State | In-memory JavaScript (no backend, no database) |
| Hosting | Static — runs locally or on any static host |

***

## Prerequisites

All you need is a modern web browser. There is no Node.js, no npm, no build tool, and no server required.

- **Browser:** Chrome 110+, Firefox 110+, Safari 16+, or Edge 110+
- **Internet connection:** Required on first load only (for CDN fonts and icons)

***

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/shopflow.git
cd shopflow
```

### 2. Open the App

**Option A — Direct file open (simplest):**

```bash
open shopflow.html
# or on Windows:
start shopflow.html
# or on Linux:
xdg-open shopflow.html
```

**Option B — Local server (recommended to avoid any CDN/CORS issues):**

If you have Python installed:

```bash
# Python 3
python3 -m http.server 8080

# Python 2
python -m SimpleHTTPServer 8080
```

Then open your browser and go to:

```
http://localhost:8080/shopflow.html
```

If you have Node.js installed:

```bash
npx serve .
```

Then open the URL printed in your terminal.

***

## File Structure

```
shopflow/
├── shopflow.html        ← Main app — open this in your browser
├── README.md            ← You are here
└── assets/
    └── (any locally saved images or icons)
```

Everything lives in `shopflow.html`. Styles and scripts are embedded inline — no separate CSS or JS files to manage.

***

## How to Use the App

1. **Select the vehicle** — Enter the year, make, and model in the left input panel.
2. **Choose a service** — Search or select from the service dropdown (e.g., Brake Pad Replacement, Oil Change, Transmission Flush). Labor time and suggested parts cost range auto-fill.
3. **Adjust the estimate** — Edit labor hours, parts cost, and markup percentage as needed. Toggle the Diagnostic Fee on or off and set the amount.
4. **Set approval status** — Use the Customer Approval Status dropdown to mark the job as Pending, Approved, or Declined.
5. **Review the repair order** — The right panel updates in real time with a full line-item breakdown and total.
6. **Copy the Job Summary** — Click the copy button in the Job Summary Box to grab the one-sentence plain-English quote for texting or emailing the customer.

***

## Tooltips Reference

| Field | Tooltip |
|---|---|
| **Labor Hours** | Use your flat-rate labor guide if you're unsure — most brake jobs run 1.5–2.5 hrs |
| **Parts Cost** | Enter your cost or the suggested range — you can adjust markup below |
| **Markup %** | Most shops charge 20–40% parts markup to cover ordering and handling |

***

## Customization

### Change Default Labor Rate

Open `shopflow.html` in any text editor and search for:

```javascript
const DEFAULT_LABOR_RATE = 95;
```

Update the value to match your shop's hourly rate.

### Add New Services

Search for the `SERVICES` array in the script block and add entries following this structure:

```javascript
{
  name: "Timing Belt Replacement",
  laborHours: 4.5,
  partsRangeLow: 150,
  partsRangeHigh: 350
}
```

### Change the Shop Name

Search for `ShopFlow` in the HTML and replace it with your shop's name. It appears in the header logo and the generated repair order output.

***

## Deployment (Optional)

Since this is a fully static app, it can be deployed to any static host with zero configuration:

| Host | Command / Steps |
|---|---|
| **GitHub Pages** | Push to `main`, enable Pages in repo Settings → Pages |
| **Netlify** | Drag and drop the project folder at netlify.com/drop |
| **Vercel** | `npx vercel` from the project directory |
| **Cloudflare Pages** | Connect repo in the Cloudflare dashboard |

No build settings required — just point the host at `shopflow.html` as the root file.

***

## Known Limitations

- **No data persistence** — estimates are in-memory only. Refreshing the page clears all data. A future version will add local file export (PDF or CSV).
- **No customer database** — customer profiles and service history are on the roadmap, not yet implemented.
- **Static service list** — the service catalog is hardcoded. Future versions will support a customizable shop-specific catalog.

***

## Roadmap

- [ ] Export repair order as PDF
- [ ] Save and load estimates as JSON files
- [ ] Customer profile and vehicle history
- [ ] Parts inventory tracking
- [ ] Multi-technician job assignment
- [ ] SMS/email quote delivery integration

***

## Contributing

Pull requests are welcome. For major changes, please open an issue first to describe what you'd like to change.

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m 'Add your feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a pull request

***

## License

MIT License — free to use, modify, and distribute. See `LICENSE` for details.

***

## Contact

Built by **Chemal Chevannes** — Royal Palm Beach, FL  
For questions or feedback, open a GitHub issue or reach out directly through the repository.
