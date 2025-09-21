# adataguy.in

WEBSITE --> https://adataguy.in

This repository contains code for my personal website or portfolio built using a Bootstrap template (see license info).

## Key Features & Benefits

*   **Responsive Design:** Utilizes Bootstrap for a mobile-friendly layout.
*   **Portfolio Showcase:** Designed to display projects, skills, and experience.
*   **Clean and Modern Interface:** Leverages the FolioOne Bootstrap template for a professional look.
*   **Customizable:**  Built to be easily adapted to individual needs and branding.

## Prerequisites & Dependencies

*   **Web Browser:**  A modern web browser (Chrome, Firefox, Safari, etc.) to view the website.
*   **Text Editor:** A text editor or IDE (VS Code, Sublime Text, Atom, etc.) to modify the code.
*   **Web Server (Optional):**  If running locally, a web server (e.g., Apache, Nginx) is required.
*   **JavaScript:** For interactive elements and front-end functionality.

## Installation & Setup Instructions

1.  **Download the Repository:** Clone or download the repository to your local machine.

    ```bash
    git clone https://github.com/MayurakshaSikdar/adataguy.in.git
    ```

2.  **Navigate to the Directory:** Change your current directory to the project folder.

    ```bash
    cd adataguy.in
    ```

3.  **Open in Browser:** Open the `index.html` file (or any other HTML file in the root) in your web browser to view the website.

4.  **(Optional) Run on a Web Server:**  If you need to test PHP functionality or have specific server-side requirements:

    *   Configure a web server (e.g., Apache, Nginx) to serve the project directory.
    *   Place the project files in the appropriate web server directory (e.g., `htdocs` for Apache).
    *   Access the website through your web server's address (e.g., `http://localhost/`).

## Usage Examples & API Documentation (if applicable)

This project primarily uses HTML, CSS, and JavaScript to create a static website.  There are no external APIs documented in the provided information. PHP is utilized, but without further details about its usage or included libraries, API documentation isn't relevant.
To customize the website:

*   **Edit HTML:**  Modify the HTML files (`index.html`, etc.) to change the content and structure of the website.
*   **Customize CSS:**  Edit the `assets/css/main.css` file to change the appearance and styling.
*   **Add JavaScript:**  Modify the `assets/js/main.js` file to add interactive features or custom functionality.

## Configuration Options

There are no specific configuration files or environment variables mentioned in the provided files. Configuration is achieved by directly modifying the HTML, CSS, and JavaScript files.  Specifically:

*   **`assets/css/main.css`:** Change colors, fonts, and layout.
*   **`assets/js/main.js`:** Configure Javascript behavior.
*   **HTML files:**  Modify content, links and meta-data

## Contributing Guidelines

1.  **Fork the Repository:** Fork the repository to your own GitHub account.
2.  **Create a Branch:** Create a new branch for your changes.

    ```bash
    git checkout -b feature/<your-feature-name>
    ```

3.  **Make Changes:** Implement your changes, ensuring to follow the project's coding style and conventions.
4.  **Commit Changes:** Commit your changes with clear and descriptive commit messages.

    ```bash
    git commit -m "Add your descriptive commit message"
    ```

5.  **Push to Fork:** Push your changes to your forked repository.

    ```bash
    git push origin feature/<your-feature-name>
    ```

6.  **Create a Pull Request:** Create a pull request from your branch to the main repository.

## License Information

This project uses the **FolioOne** Bootstrap template, which is licensed under the [Bootstrapmade](https://bootstrapmade.com/license/) license.  Please refer to the license for the terms and conditions of using this template.

## Acknowledgments

This project is based on the **FolioOne** Bootstrap template created by [BootstrapMade](https://bootstrapmade.com/).


## Deployment

This website is deployed as a **static site on AWS**, using the following services:  

1. **Amazon S3 (Static Website Hosting):**  
   * The website files (HTML, CSS, JS, assets) are hosted in an S3 bucket with static website hosting enabled.  
   * Bucket configured for public access via CloudFront only (restricted direct S3 access).  

2. **Amazon CloudFront (CDN & HTTPS):**  
   * A CloudFront distribution is set up in front of the S3 bucket to provide low latency, global caching, and HTTPS access.  
   * The distribution is linked with an SSL/TLS certificate from AWS Certificate Manager (ACM).  

3. **AWS Certificate Manager (ACM):**  
   * A free SSL/TLS certificate was provisioned and attached to CloudFront for secure HTTPS traffic.  

4. **Amazon Route 53 (DNS):**  
   * Hosted zone in Route 53 manages DNS records for the domain.  
   * An **Alias record (A record)** points the domain to the CloudFront distribution.  

5. **GoDaddy Domain:**  
   * The custom domain (adataguy.in) was purchased via GoDaddy.  
   * The domain’s **nameservers** were updated to use the Route 53 hosted zone, enabling AWS DNS management.  

### Deployment Workflow  
- Build and update website files locally.  
- Sync files to S3 bucket:  
    ```bash
    aws s3 sync ./ s3://<bucket-name> --delete
    ```