<script>
    import Article from "$lib/components/Article.svelte";
    import { companyName } from "../data";
</script>

<Article>
    <h1>
        Privacy Policy for {companyName}:
    </h1>
    <p>
        This Privacy Policy describes how {companyName} collects, uses, discloses,
        and protects the personal information of individuals who interact with our
        website and services. Please read this policy carefully to understand our
        practices regarding your personal information.
    </p>

    <ul>
        <li>
            <h3>Information Collection and Use:</h3>
            <ul>
                <li>
                    <h4>Personal Information</h4>
                    We may collect personal information,
                    such as your name, email address, contact details, and any
                    other information you voluntarily provide when contacting
                    us, subscribing to our newsletters, or using our services.
                    We use this information to respond to your inquiries,
                    provide the requested services, and communicate with you
                    about our products and promotions.
                </li>
                <li>
                    <h4>Log Data</h4>
                    Like many websites, we may collect certain
                    non-personal information automatically when you visit our
                    website. This may include your IP address, browser type,
                    operating system, referring URLs, and other technical
                    information. We use this information to analyze trends,
                    administer the site, and gather demographic information for
                    aggregate use.
                </li>
            </ul>
        </li>
        <li>
            <h3>Information Sharing and Disclosure:</h3>
            <ul>
                <li>
                    <h4>Third-Party Service Providers</h4>
                    We may share your personal
                    information with trusted third-party service providers who
                    assist us in operating our website, conducting our business,
                    or providing services to you. These providers are
                    contractually obligated to protect your information and use
                    it solely for the purposes specified by us.
                </li>
                <li>
                    <h4>Legal Requirements</h4>
                    We may disclose your personal
                    information if required to do so by law or in response to a
                    valid legal request from governmental authorities, such as a
                    court order or subpoena.
                </li>
            </ul>
        </li>
        <li>
            <h3>Data Security:</h3>
            <p>
                We implement appropriate technical and organizational measures
                to protect your personal information from unauthorized access,
                use, alteration, or disclosure. However, please note that no
                method of transmission over the internet or electronic storage
                is 100% secure. We strive to use commercially acceptable means
                to protect your personal information, but we cannot guarantee
                its absolute security.
            </p>
        </li>
        <li>
            <h3>Cookies and Tracking Technologies:</h3>
            <p>
                We may use cookies and similar tracking technologies to enhance
                your experience on our website, analyze usage patterns, and
                deliver personalized content. You can adjust your browser
                settings to refuse cookies or notify you when cookies are being
                sent. However, please note that certain features of our website
                may not function properly if cookies are disabled.
            </p>
        </li>
        <li>
            <h3>Links to Third-Party Websites:</h3>
            <p>
                Our website may contain links to third-party websites that are
                not operated or controlled by us. This Privacy Policy applies
                only to our website. We are not responsible for the privacy
                practices or content of third-party websites. We encourage you
                to review the privacy policies of those websites before
                providing any personal information.
            </p>
        </li>
        <li>
            <h3>Children's Privacy:</h3>
            <p>
                Our website and services are not intended for individuals under
                the age of 18. We do not knowingly collect personal information
                from children. If we become aware that we have inadvertently
                collected personal information from a child, we will take steps
                to delete such information from our records.
            </p>
        </li>
        <li>
            <h3>Changes to this Privacy Policy:</h3>
            <p>
                We reserve the right to update or modify this Privacy Policy at
                any time. Any changes will be effective immediately upon posting
                the updated policy on our website. Your continued use of our
                website or services after any changes to the Privacy Policy will
                signify your acceptance of those changes.
            </p>
        </li>
        <li>
            <h3>Contact Us:</h3>
            <p>
                If you have any questions or concerns about this Privacy Policy
                or our privacy practices, please contact us using the
                information provided on our website.
            </p>
        </li>
    </ul>
</Article>

<style>
    ul {
        counter-reset: section;
        list-style-type: none;
    }

</style>
