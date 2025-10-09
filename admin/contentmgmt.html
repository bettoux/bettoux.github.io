<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Facettes CMS Admin (Local Storage)</title>
    <!-- Load Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Load Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        /* Custom styles for a polished, professional look */
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f7f7f7;
            min-height: 100vh;
        }
        .card {
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1), 0 5px 10px -5px rgba(0, 0, 0, 0.04);
        }
        .form-input {
            transition: all 0.2s;
            border-color: #e5e7eb;
        }
        .form-input:focus {
            border-color: #6366f1; /* Indigo-500 */
            box-shadow: 0 0 0 1px #6366f1;
        }
        .btn-primary {
            transition: background-color 0.2s, transform 0.1s;
        }
        .btn-primary:hover {
            background-color: #4f46e5; /* Indigo-600 */
        }
        .btn-primary:active {
            transform: scale(0.98);
        }
        /* Custom styles for JSON viewer */
        #json-content {
            white-space: pre;
            overflow-x: auto;
            max-height: 70vh;
            font-family: monospace;
            background-color: #1e293b; /* Slate-800 */
            color: #e2e8f0; /* Slate-200 */
            padding: 1rem;
            border-radius: 0.75rem;
        }
        /* Custom styles for Preview Modal - ensures full screen view */
        #preview-modal .modal-content-area {
            max-width: 90%;
            max-height: 90vh;
            overflow-y: auto;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800">

    <div id="app" class="min-h-screen flex flex-col">
        <!-- Main Application Content -->
    </div>

    <script type="module">
        // --- AUTHENTICATION STATE (Hardcoded Credentials) ---
        let adminUsername = 'facettes';
        let adminPassword = 'bettara';
        let isAuthenticated = false;

        // --- APP STATE ---
        // contentData stores the JSON structure loaded from localStorage
        let contentData = { en: {}, fr: {} };
        let activeLanguage = 'en';
        let activeContentType = 'Text Content'; // Default
        const contentTypes = [
            'Text Content',
            'Speaker Information',
            'Services Information',
            'Form & Contact Labels',
            'Navigation & Footer',
        ];

        // Content Keys Mapping (based on content_guide.md)
        const KEY_MAPS = {
            'Text Content': [
                { key: 'hero_tagline', label: 'Hero Headline', type: 'text' },
                { key: 'hero_subheading', label: 'Hero Subtitle', type: 'text' },
                { key: 'hero_cta', label: 'Hero CTA Button', type: 'text' },
                { key: 'speakers_heading', label: 'Speakers Section Title', type: 'text' },
                { key: 'speakers_subtext', label: 'Speakers Section Subtitle', type: 'text' },
                { key: 'services_heading', label: 'Services Section Title', type: 'text' },
                { key: 'services_subtext', label: 'Services Section Subtitle', type: 'text' },
                { key: 'contact_heading', label: 'Contact Section Title', type: 'text' },
                { key: 'contact_tagline', label: 'Contact Section Subtitle', type: 'text' },
            ],
            'Navigation & Footer': [
                { key: 'nav_speakers', label: 'Nav: Speakers (Desktop)', type: 'text' },
                { key: 'nav_services', label: 'Nav: Services (Desktop)', type: 'text' },
                { key: 'nav_contact', label: 'Nav: Contact (Desktop)', type: 'text' },
                { key: 'nav_speakers_mobile', label: 'Nav: Speakers (Mobile)', type: 'text' },
                { key: 'nav_services_mobile', label: 'Nav: Services (Mobile)', type: 'text' },
                { key: 'nav_contact_mobile', label: 'Nav: Contact (Mobile)', type: 'text' },
                { key: 'footer_rights', label: 'Footer Copyright Text', type: 'text' },
            ],
            'Form & Contact Labels': [
                { key: 'form_name', label: 'Form Label: Name', type: 'text' },
                { key: 'form_email', label: 'Form Label: Email', type: 'text' },
                { key: 'form_event', label: 'Form Label: Event Type', type: 'text' },
                { key: 'form_details', label: 'Form Label: Details', type: 'text' },
                { key: 'form_submit', label: 'Button: Submit Form', type: 'text' },
                { key: 'form_generate', label: 'Button: Generate/Alt Action', type: 'text' },
                { key: 'contact_response_time', label: 'Contact Message: Response Time', type: 'text' },
                { key: 'output_heading', label: 'Contact Message: Output Heading', type: 'text' },
                { key: 'speaker_cta', label: 'Speaker Inquiry Link Text', type: 'text' },
                { key: 'detail_inquire_cta', label: 'Speaker Detail Inquiry Button', type: 'text' },
            ],
            'Services Information': [
                // Service 1
                { key: 'service_1_title', label: 'Service 1 Title', type: 'text' },
                { key: 'service_1_description', label: 'Service 1 Description', type: 'textarea' },
                // Service 2
                { key: 'service_2_title', label: 'Service 2 Title', type: 'text' },
                { key: 'service_2_description', label: 'Service 2 Description', type: 'textarea' },
                // Service 3
                { key: 'service_3_title', label: 'Service 3 Title', type: 'text' },
                { key: 'service_3_description', label: 'Service 3 Description', type: 'textarea' },
            ],
            // Speaker Information is handled by a dedicated function
        };

        // --- INITIAL DATA BOOTSTRAP (For first-time use) ---
        const initialContent = {
            en: {
                nav_speakers: "Speakers", nav_services: "Services", nav_contact: "Contact",
                nav_speakers_mobile: "Speakers", nav_services_mobile: "Services", nav_contact_mobile: "Contact",
                hero_tagline: "Crafting the Future of Innovation", hero_subheading: "Bespoke strategies and insights from industry leaders.", hero_cta: "Explore Services",
                speakers_heading: "Meet Our Experts", speakers_subtext: "Thought leaders shaping tomorrow's landscape.",
                service_1_title: "Keynote Speaking", service_1_description: "Engaging presentations tailored for your event.",
                service_2_title: "Executive Workshops", service_2_description: "Hands-on sessions for strategic teams.",
                service_3_title: "Innovation Consulting", service_3_description: "Deep dive analysis and roadmap development.",
                contact_heading: "Get in Touch", contact_tagline: "Let's discuss your next breakthrough.",
                form_name: "Your Name", form_email: "Email Address", form_event: "Event Type", form_details: "Project Details",
                form_submit: "Submit Inquiry", form_generate: "Generate Quote", contact_response_time: "We aim to respond within 24 hours.",
                output_heading: "Thank You!", speaker_cta: "Inquire Now", detail_inquire_cta: "Book Speaker",
                detail_back: "Back to Roster", detail_focus_areas: "Focus Areas", detail_biography: "Biography",
                footer_rights: "© 2024 Facettes. All Rights Reserved.",
                speakers: {
                    john_doe: { name: "John Doe", title: "Future Tech Strategist", bio_long: "John is a visionary leader with over 20 years in emerging technologies.", focus: ["AI Strategy", "Future Tech", "M&A"], image_url: "https://placehold.co/100x100/1e293b/ffffff?text=JD" },
                    jane_smith: { name: "Jane Smith", title: "Digital Transformation Expert", bio_long: "Jane specializes in large-scale digital transformation and change management.", focus: ["Digital", "Leadership", "Change"], image_url: "https://placehold.co/100x100/1e293b/ffffff?text=JS" },
                }
            },
            fr: {
                nav_speakers: "Conférenciers", nav_services: "Services", nav_contact: "Contact",
                nav_speakers_mobile: "Conférenciers", nav_services_mobile: "Services", nav_contact_mobile: "Contact",
                hero_tagline: "Façonner l'Avenir de l'Innovation", hero_subheading: "Stratégies et aperçus sur mesure de leaders de l'industrie.", hero_cta: "Explorer les Services",
                speakers_heading: "Rencontrez Nos Experts", speakers_subtext: "Leaders d'opinion qui façonnent le paysage de demain.",
                service_1_title: "Conférences", service_1_description: "Présentations engageantes adaptées à votre événement.",
                service_2_title: "Ateliers Exécutifs", service_2_description: "Sessions pratiques pour les équipes stratégiques.",
                service_3_title: "Consultation en Innovation", service_3_description: "Analyse approfondie et développement de feuille de route.",
                contact_heading: "Contactez-nous", contact_tagline: "Discutons de votre prochaine percée.",
                form_name: "Votre Nom", form_email: "Adresse E-mail", form_event: "Type d'événement", form_details: "Détails du projet",
                form_submit: "Soumettre la Demande", form_generate: "Générer un Devis", contact_response_time: "Nous nous efforçons de répondre dans les 24 heures.",
                output_heading: "Merci!", speaker_cta: "Renseignez-vous maintenant", detail_inquire_cta: "Réserver",
                detail_back: "Retour à la Liste", detail_focus_areas: "Domaines de Spécialité", detail_biography: "Biographie",
                footer_rights: "© 2024 Facettes. Tous droits réservés.",
                speakers: {
                    john_doe: { name: "Jean Dupont", title: "Stratège Tech Future", bio_long: "Jean est un leader visionnaire avec plus de 20 ans dans les technologies émergentes.", focus: ["Stratégie IA", "Tech Future", "F&A"], image_url: "https://placehold.co/100x100/1e293b/ffffff?text=JD" },
                    jane_smith: { name: "Jeanne Smith", title: "Experte en Transformation Digitale", bio_long: "Jeanne est spécialisée dans la transformation numérique à grande échelle et la gestion du changement.", focus: ["Numérique", "Leadership", "Changement"], image_url: "https://placehold.co/100x100/1e293b/ffffff?text=JS" },
                }
            }
        };

        // --- UTILITY FUNCTIONS ---
        const $ = (selector) => document.querySelector(selector);
        const $$ = (selector) => document.querySelectorAll(selector);

        // Simple custom non-blocking message box replacement for alert()
        const showMessage = (title, message, type = 'info') => {
            const container = $('#message-container');
            if (!container) return;

            const colorMap = {
                success: 'bg-green-100 border-green-400 text-green-700',
                error: 'bg-red-100 border-red-400 text-red-700',
                info: 'bg-blue-100 border-blue-400 text-blue-700'
            };

            const html = `
                <div class="p-4 border ${colorMap[type]} rounded-xl mb-4 opacity-0 transition-opacity duration-300" role="alert">
                    <strong class="font-bold">${title}</strong>
                    <span class="block sm:inline">${message}</span>
                </div>
            `;
            container.innerHTML = html;
            const msgElement = container.querySelector('div');
            setTimeout(() => msgElement.classList.remove('opacity-0'), 10);
            setTimeout(() => msgElement.classList.add('opacity-0'), 5000);
            setTimeout(() => container.innerHTML = '', 5300);
        };
        
        // Generic modal close function
        function hideModal(id) {
            const modal = $(`#${id}`);
            if (modal) {
                modal.classList.remove('flex');
                modal.classList.add('hidden');
            }
        }


        // --- LOCAL STORAGE DATA HANDLING ---

        function loadContentFromLocalStorage() {
            try {
                // Keys used in localStorage: 'cms_content_en' and 'cms_content_fr'
                const enContent = localStorage.getItem('cms_content_en');
                const frContent = localStorage.getItem('cms_content_fr');

                if (enContent && frContent) {
                    contentData.en = JSON.parse(enContent);
                    contentData.fr = JSON.parse(frContent);
                    console.log("Content loaded from localStorage.");
                } else {
                    // Bootstrap initial data if not found in localStorage
                    contentData.en = initialContent.en;
                    contentData.fr = initialContent.fr;
                    // Save initial content to localStorage without showing a message
                    saveContentToLocalStorage('en', contentData.en, false);
                    saveContentToLocalStorage('fr', contentData.fr, false);
                    showMessage('Info', 'Initial content structure bootstrapped to Local Storage.', 'info');
                }
            } catch (error) {
                console.error("Error loading/parsing content from localStorage:", error);
                showMessage('Error', 'Failed to load content. Using default initial data.', 'error');
                contentData.en = initialContent.en;
                contentData.fr = initialContentContent.fr;
            }
        }

        function saveContentToLocalStorage(language, data, showMsg = true) {
            try {
                // Update in-memory data
                contentData[language] = data;

                // Save to localStorage
                localStorage.setItem(`cms_content_${language}`, JSON.stringify(data));

                if (showMsg) {
                    showMessage('Success', `${activeContentType} content updated successfully for ${language.toUpperCase()} (Saved Locally).`, 'success');
                }
                // Rerender the editor to reflect the new state immediately
                renderContentEditor();

            } catch (error) {
                console.error("Error saving content to localStorage:", error);
                showMessage('Error', 'Failed to save content to Local Storage.', 'error');
            }
        }

        // --- AUTHENTICATION/SECURITY LOGIC ---

        function handleLogin(event) {
            event.preventDefault();
            const form = event.target;
            const username = form.username.value;
            const password = form.password.value;

            if (username === adminUsername && password === adminPassword) {
                isAuthenticated = true;
                localStorage.setItem('admin_auth_status', 'true'); // Simulate session
                render();
            } else {
                showMessage('Error', 'Invalid username or password.', 'error');
            }
            form.reset();
        }

        function handleLogout() {
            isAuthenticated = false;
            localStorage.removeItem('admin_auth_status');
            render();
        }

        function handleChangePassword(event) {
            event.preventDefault();
            const form = event.target;
            const currentPass = form.current_password.value;
            const newPass = form.new_password.value;
            const confirmPass = form.confirm_password.value;

            if (currentPass !== adminPassword) {
                showMessage('Error', 'Current password is incorrect.', 'error');
                return;
            }
            if (newPass.length < 5) {
                showMessage('Error', 'New password must be at least 5 characters long.', 'error');
                return;
            }
            if (newPass !== confirmPass) {
                showMessage('Error', 'New passwords do not match.', 'error');
                return;
            }

            adminPassword = newPass; // Update hardcoded password
            showMessage('Success', 'Password updated successfully!', 'success');
            form.reset();
            hideModal('password-modal');
        }

        function handleResetPassword() {
            adminPassword = 'bettara'; // Reset to default
            showMessage('Success', 'Password reset to default (bettara).', 'success');
            hideModal('password-modal');
        }

        // --- RENDERING FUNCTIONS ---

        function renderLoginForm() {
            const html = `
                <div class="flex items-center justify-center min-h-screen bg-gray-100 p-4">
                    <div class="w-full max-w-md bg-white card rounded-2xl p-8 space-y-6">
                        <div class="text-center">
                            <i data-lucide="lock" class="mx-auto h-10 w-10 text-indigo-600"></i>
                            <h2 class="mt-4 text-3xl font-extrabold text-gray-900">
                                Sign in to CMS Admin
                            </h2>
                            <p class="mt-2 text-sm text-gray-600">
                                Use the credentials: <code>facettes</code> / <code>bettara</code>
                            </p>
                        </div>
                        <form id="login-form" class="space-y-6">
                            <div>
                                <label for="username" class="block text-sm font-medium text-gray-700">Username</label>
                                <input id="username" name="username" type="text" required class="form-input mt-1 block w-full px-4 py-2 border rounded-xl" placeholder="facettes">
                            </div>
                            <div>
                                <label for="password" class="block text-sm font-medium text-gray-700">Password</label>
                                <input id="password" name="password" type="password" required class="form-input mt-1 block w-full px-4 py-2 border rounded-xl" placeholder="*******">
                            </div>
                            <button type="submit" class="w-full flex justify-center py-3 px-4 border border-transparent rounded-xl shadow-sm text-sm font-medium text-white bg-indigo-500 btn-primary focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                                Sign In
                            </button>
                        </form>

                        <div id="message-container"></div>
                    </div>
                </div>
            `;
            $('#app').innerHTML = html;
            lucide.createIcons();
            $('#login-form').addEventListener('submit', handleLogin);
        }

        function renderAdminDashboard() {
            const langLabel = activeLanguage === 'en' ? 'English (en.json)' : 'French (fr.json)';
            const html = `
                <nav class="bg-white card shadow-sm sticky top-0 z-10">
                    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                        <div class="flex justify-between h-16">
                            <div class="flex items-center">
                                <span class="text-2xl font-bold text-indigo-600">Facettes CMS</span>
                                <span class="ml-4 px-3 py-1 text-xs font-semibold rounded-full bg-indigo-100 text-indigo-700">${langLabel}</span>
                            </div>
                            <div class="flex items-center space-x-4">
                                <button id="preview-btn" class="text-sm font-medium text-gray-600 hover:text-indigo-600 transition-colors flex items-center">
                                    <i data-lucide="eye" class="w-4 h-4 mr-1"></i> Preview Website
                                </button>
                                <button id="change-pass-btn" class="text-sm font-medium text-gray-600 hover:text-indigo-600 transition-colors flex items-center">
                                    <i data-lucide="key" class="w-4 h-4 mr-1"></i> Change Password
                                </button>
                                <button id="logout-btn" class="text-sm font-medium text-red-500 hover:text-red-700 transition-colors flex items-center">
                                    <i data-lucide="log-out" class="w-4 h-4 mr-1"></i> Logout
                                </button>
                            </div>
                        </div>
                    </div>
                </nav>

                <div class="max-w-7xl mx-auto py-8 sm:px-6 lg:px-8 flex-grow">
                    <div id="message-container"></div>
                    <div class="flex flex-col lg:flex-row space-y-8 lg:space-y-0 lg:space-x-8">
                        
                        <!-- Sidebar for Selection -->
                        <div class="lg:w-1/4">
                            <div class="bg-white card rounded-2xl p-6 shadow-md sticky top-20">
                                <h3 class="text-xl font-semibold text-gray-900 mb-4 border-b pb-2">Settings</h3>

                                <!-- Language Selection (File Selection) -->
                                <div class="mb-6">
                                    <label class="block text-sm font-medium text-gray-700 mb-2">Language File</label>
                                    <select id="lang-select" class="form-input block w-full px-3 py-2 rounded-xl text-base">
                                        <option value="en" ${activeLanguage === 'en' ? 'selected' : ''}>English (en.json)</option>
                                        <option value="fr" ${activeLanguage === 'fr' ? 'selected' : ''}>French (fr.json)</option>
                                    </select>
                                </div>

                                <!-- Content Type Selection -->
                                <div>
                                    <label class="block text-sm font-medium text-gray-700 mb-2">Content Type</label>
                                    <div class="space-y-1">
                                        ${contentTypes.map(type => `
                                            <button data-type="${type}" class="content-type-btn block w-full text-left px-3 py-2 rounded-xl text-sm font-medium transition-colors ${activeContentType === type ? 'bg-indigo-500 text-white shadow-md' : 'text-gray-700 hover:bg-gray-100'}">
                                                ${type}
                                            </button>
                                        `).join('')}
                                    </div>
                                </div>

                                <!-- JSON Export -->
                                <div class="mt-6 pt-4 border-t">
                                    <button id="view-json-btn" class="w-full py-2 px-4 border border-indigo-200 rounded-xl shadow-sm text-sm font-medium text-indigo-700 bg-indigo-50 hover:bg-indigo-100 transition-colors">
                                        <i data-lucide="file-json" class="w-4 h-4 inline mr-1"></i> View/Export ${activeLanguage.toUpperCase()}.json
                                    </button>
                                </div>
                            </div>
                        </div>

                        <!-- Content Editor -->
                        <div class="lg:w-3/4">
                            <div class="bg-white card rounded-2xl p-8 shadow-md">
                                <h3 class="text-2xl font-bold text-gray-900 mb-6">${activeContentType} Editor</h3>
                                <div id="content-editor-form-container">
                                    <!-- Dynamic forms will be rendered here -->
                                </div>
                            </div>
                        </div>

                    </div>
                </div>

                <!-- Password Modal -->
                <div id="password-modal" class="fixed inset-0 bg-gray-900 bg-opacity-75 hidden items-center justify-center p-4 z-50">
                    <div class="bg-white card rounded-2xl w-full max-w-lg p-8 space-y-6">
                        <h3 class="text-xl font-bold border-b pb-2 flex justify-between items-center">
                            Change Administrator Password
                            <button onclick="hideModal('password-modal')"><i data-lucide="x" class="w-5 h-5 text-gray-500 hover:text-gray-800"></i></button>
                        </h3>
                        <form id="change-pass-form" class="space-y-4">
                            <div>
                                <label for="current_password" class="block text-sm font-medium text-gray-700">Current Password</label>
                                <input id="current_password" name="current_password" type="password" required class="form-input mt-1 block w-full px-4 py-2 border rounded-xl">
                            </div>
                            <div>
                                <label for="new_password" class="block text-sm font-medium text-gray-700">New Password</label>
                                <input id="new_password" name="new_password" type="password" required class="form-input mt-1 block w-full px-4 py-2 border rounded-xl">
                            </div>
                            <div>
                                <label for="confirm_password" class="block text-sm font-medium text-gray-700">Confirm New Password</label>
                                <input id="confirm_password" name="confirm_password" type="password" required class="form-input mt-1 block w-full px-4 py-2 border rounded-xl">
                            </div>
                            <div class="flex justify-between items-center pt-2">
                                <button type="button" id="reset-pass-btn" class="text-sm text-red-500 hover:text-red-700">Reset to Default (bettara)</button>
                                <button type="submit" class="py-2 px-4 border border-transparent rounded-xl shadow-sm text-sm font-medium text-white bg-indigo-500 btn-primary">
                                    Save New Password
                                </button>
                            </div>
                        </form>
                    </div>
                </div>

                <!-- JSON Export Modal -->
                <div id="json-modal" class="fixed inset-0 bg-gray-900 bg-opacity-75 hidden items-center justify-center p-4 z-50">
                    <div class="bg-white card rounded-2xl w-full max-w-4xl p-6 space-y-4 modal-content-area">
                        <h3 class="text-xl font-bold border-b pb-2 flex justify-between items-center">
                            Raw Content JSON: ${activeLanguage.toUpperCase()}.json
                            <button onclick="hideModal('json-modal')"><i data-lucide="x" class="w-5 h-5 text-gray-500 hover:text-gray-800"></i></button>
                        </h3>
                        <pre id="json-content" class="rounded-xl text-xs"></pre>
                        <button onclick="copyJsonToClipboard()" class="w-full py-2 px-4 border border-transparent rounded-xl shadow-sm text-sm font-medium text-white bg-indigo-500 btn-primary">
                            <i data-lucide="copy" class="w-4 h-4 inline mr-1"></i> Copy JSON to Clipboard
                        </button>
                    </div>
                </div>

                <!-- Website Preview Modal -->
                <div id="preview-modal" class="fixed inset-0 bg-gray-900 bg-opacity-75 hidden justify-center p-4 z-50">
                    <div class="bg-white card rounded-2xl w-full p-6 space-y-4 modal-content-area">
                        <h3 class="text-xl font-bold border-b pb-2 flex justify-between items-center">
                            Website Content Preview
                            <button onclick="hideModal('preview-modal')"><i data-lucide="x" class="w-5 h-5 text-gray-500 hover:text-gray-800"></i></button>
                        </h3>
                        <div id="preview-content" class="text-sm">
                            <!-- Preview content rendered here -->
                        </div>
                    </div>
                </div>

                <!-- Delete Confirmation Modal (Generic) -->
                <div id="delete-confirm-modal" class="fixed inset-0 bg-gray-900 bg-opacity-75 hidden items-center justify-center p-4 z-50">
                    <div class="bg-white card rounded-2xl w-full max-w-sm p-6 space-y-4 text-center">
                        <i data-lucide="alert-triangle" class="mx-auto h-12 w-12 text-red-500"></i>
                        <h3 class="text-xl font-bold text-gray-900">Confirm Deletion</h3>
                        <p id="delete-confirm-message" class="text-gray-600">Are you sure you want to delete this item? This action cannot be undone.</p>
                        <div class="flex justify-center space-x-4 pt-2">
                            <button onclick="hideModal('delete-confirm-modal')" class="py-2 px-4 rounded-xl text-sm font-medium text-gray-700 border hover:bg-gray-100">Cancel</button>
                            <button id="confirm-delete-btn" class="py-2 px-4 rounded-xl text-sm font-medium text-white bg-red-600 hover:bg-red-700 transition-colors">Delete</button>
                        </div>
                    </div>
                </div>
            `;
            $('#app').innerHTML = html;
            lucide.createIcons();

            // Setup listeners
            $('#logout-btn').addEventListener('click', handleLogout);
            $('#lang-select').addEventListener('change', (e) => {
                activeLanguage = e.target.value;
                renderAdminDashboard();
            });
            $$('.content-type-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    activeContentType = e.target.dataset.type;
                    renderAdminDashboard();
                });
            });
            // Password Modal
            $('#change-pass-btn').addEventListener('click', () => {
                $('#password-modal').classList.remove('hidden');
                $('#password-modal').classList.add('flex');
            });
            $('#change-pass-form').addEventListener('submit', handleChangePassword);
            $('#reset-pass-btn').addEventListener('click', handleResetPassword);

            // Preview & JSON View
            $('#preview-btn').addEventListener('click', showPreviewModal);
            $('#view-json-btn').addEventListener('click', viewJsonExport);


            // Render the specific content form
            renderContentEditor();
        }

        function renderContentEditor() {
            const container = $('#content-editor-form-container');
            if (!container) return; // Wait for dashboard to be rendered

            container.innerHTML = '';
            // Data is pulled from the in-memory contentData object, which is synchronized with localStorage
            const data = contentData[activeLanguage] || {};
            let formHtml = '';

            switch (activeContentType) {
                case 'Speaker Information':
                    formHtml = renderSpeakersForm(data.speakers || {});
                    break;
                case 'Text Content':
                case 'Navigation & Footer':
                case 'Services Information':
                case 'Form & Contact Labels':
                    const keys = KEY_MAPS[activeContentType] || [];
                    formHtml = renderGenericForm(keys, data);
                    break;
                default:
                    formHtml = `<p class="text-gray-500">Select a content type to start editing.</p>`;
            }

            container.innerHTML = formHtml;
            setupFormListeners(activeContentType, data);
        }

        function renderGenericForm(keys, data) {
            let html = `<form id="generic-form" class="space-y-6">`;
            keys.forEach(({ key, label, type }) => {
                const value = data[key] || '';
                const id = `input-${key}`;

                html += `
                    <div class="border p-4 rounded-xl bg-gray-50">
                        <label for="${id}" class="block text-sm font-semibold text-gray-700 flex justify-between items-center">
                            ${label}
                            <code class="text-xs text-indigo-500 font-mono">${key}</code>
                        </label>
                        ${type === 'textarea' ?
                            `<textarea id="${id}" name="${key}" rows="3" class="form-input mt-1 block w-full px-4 py-2 border rounded-xl">${value}</textarea>` :
                            `<input id="${id}" name="${key}" type="text" value="${value}" class="form-input mt-1 block w-full px-4 py-2 border rounded-xl">`
                        }
                    </div>
                `;
            });
            html += `<button type="submit" class="w-full py-3 px-4 rounded-xl shadow-sm text-lg font-medium text-white bg-indigo-600 btn-primary">Save All ${activeContentType}</button>`;
            html += `</form>`;
            return html;
        }

        function renderSpeakersForm(speakers) {
            let html = `
                <div class="space-y-8">
                    <form id="add-speaker-form" class="bg-indigo-50 border border-indigo-200 p-6 rounded-2xl shadow-inner space-y-4">
                        <h4 class="text-lg font-bold text-indigo-800">Add New Speaker</h4>
                        <input type="text" id="new-speaker-id" placeholder="Unique ID (e.g., 'maria_gonzalez')" required class="form-input block w-full px-3 py-2 rounded-xl">
                        <button type="submit" class="w-full py-2 px-4 rounded-xl shadow-sm text-sm font-medium text-white bg-indigo-500 btn-primary">
                            Create Speaker
                        </button>
                    </form>

                    <h4 class="text-xl font-bold text-gray-900 border-b pb-2">Existing Speakers (${Object.keys(speakers).length})</h4>

                    <div id="existing-speakers-list" class="space-y-6">
            `;

            for (const [id, speaker] of Object.entries(speakers)) {
                html += `
                    <div class="speaker-card bg-gray-50 border p-5 rounded-2xl shadow-sm space-y-4">
                        <h5 class="text-lg font-bold text-indigo-600 flex justify-between items-center">
                            ${speaker.name || 'Untitled Speaker'}
                            <code class="text-xs text-gray-500 font-mono">${id}</code>
                        </h5>
                        <form data-speaker-id="${id}" class="speaker-edit-form space-y-3">
                            ${renderSpeakerField('Name', 'name', speaker.name, id)}
                            ${renderSpeakerField('Title/Role', 'title', speaker.title, id)}
                            ${renderSpeakerField('Image URL', 'image_url', speaker.image_url, id)}
                            ${renderSpeakerField('Detailed Biography (bio_long)', 'bio_long', speaker.bio_long, id, 'textarea')}
                            ${renderSpeakerField('Focus Areas (Comma Separated)', 'focus', Array.isArray(speaker.focus) ? speaker.focus.join(', ') : '', id)}

                            <div class="flex justify-end space-x-3 pt-4">
                                <button type="button" data-speaker-id="${id}" class="delete-speaker-btn text-sm font-medium text-red-600 hover:text-red-800 transition-colors">
                                    <i data-lucide="trash-2" class="w-4 h-4 inline mr-1"></i> Delete
                                </button>
                                <button type="submit" class="py-2 px-4 rounded-xl shadow-sm text-sm font-medium text-white bg-green-500 hover:bg-green-600 transition-colors">
                                    Save Changes
                                </button>
                            </div>
                        </form>
                    </div>
                `;
            }

            html += `</div></div>`;
            return html;
        }

        function renderSpeakerField(label, key, value, id, type = 'text') {
            const inputId = `${id}-${key}`;
            return `
                <div>
                    <label for="${inputId}" class="block text-sm font-medium text-gray-700">${label}</label>
                    ${type === 'textarea' ?
                        `<textarea id="${inputId}" name="${key}" rows="2" class="form-input mt-1 block w-full px-3 py-2 rounded-xl">${value || ''}</textarea>` :
                        `<input id="${inputId}" name="${key}" type="text" value="${value || ''}" class="form-input mt-1 block w-full px-3 py-2 rounded-xl">`
                    }
                </div>
            `;
        }
        
        // --- PREVIEW / EXPORT LOGIC ---

        function renderPreviewModalContent(data) {
            // A simplified mock-up of the website structure using the CMS keys
            const lang = activeLanguage.toUpperCase();
            const speakersList = Object.entries(data.speakers || {}).map(([id, speaker]) => `
                <div class="bg-white p-4 rounded-xl shadow-md border">
                    <h4 class="font-bold text-lg text-indigo-700">${speaker.name || 'N/A'} (${id})</h4>
                    <p class="text-gray-600">${speaker.title || 'N/A'}</p>
                    <p class="mt-2 text-sm text-gray-500">${(speaker.bio_long || 'N/A').substring(0, 100)}...</p>
                    <p class="mt-2 text-xs font-medium text-gray-400">Focus: ${(Array.isArray(speaker.focus) ? speaker.focus.join(', ') : speaker.focus || 'N/A')}</p>
                </div>
            `).join('');

            const servicesList = `
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    ${[1, 2, 3].map(i => {
                        // FIX: Use string concatenation instead of nested template literals which caused a Syntax Error.
                        const titleKey = 'service_' + i + '_title';
                        const descKey = 'service_' + i + '_description';
                        return `
                            <div class="bg-white p-6 rounded-xl shadow-lg border-t-4 border-indigo-500">
                                <h5 class="font-bold text-xl mb-2">${data[titleKey] || 'Service Title Missing'}</h5>
                                <p class="text-sm text-gray-600">${data[descKey] || 'Service Description Missing'}</p>
                            </div>
                        `;
                    }).join('')}
                </div>
            `;

            return `
                <div class="max-w-4xl mx-auto p-8 bg-gray-100 rounded-2xl shadow-xl space-y-12">
                    <h1 class="text-4xl font-extrabold text-center text-indigo-700">WEBSITE PREVIEW (${lang} - ${activeContentType})</h1>
                    <p class="text-center text-gray-500 text-sm">This view shows how your currently saved content appears in the mock website layout.</p>

                    <!-- Nav Labels -->
                    <div class="p-4 bg-gray-200 rounded-xl border border-gray-300 flex justify-center space-x-4 text-sm font-medium">
                        <span>${data.nav_speakers || 'Nav Speakers'}</span>
                        <span>${data.nav_services || 'Nav Services'}</span>
                        <span>${data.nav_contact || 'Nav Contact'}</span>
                    </div>

                    <!-- Hero Section -->
                    <div class="p-8 bg-indigo-100 rounded-xl border-2 border-indigo-300 space-y-4">
                        <h2 class="text-sm font-semibold uppercase text-indigo-600 tracking-wider">HERO SECTION</h2>
                        <h3 class="text-3xl font-bold text-gray-900">${data.hero_tagline || '[Hero Tagline Missing]'}</h3>
                        <p class="text-lg text-indigo-700">${data.hero_subheading || '[Hero Subheading Missing]'}</p>
                        <button class="bg-indigo-600 text-white py-2 px-6 rounded-xl font-medium">${data.hero_cta || '[CTA Missing]'}</button>
                    </div>

                    <!-- Speakers Section -->
                    <div class="space-y-6">
                        <h2 class="text-3xl font-bold text-gray-900 border-b pb-2">${data.speakers_heading || '[Speakers Heading Missing]'}</h2>
                        <p class="text-gray-600">${data.speakers_subtext || '[Speakers Subtext Missing]'}</p>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            ${speakersList.length > 0 ? speakersList : '<p class="text-gray-500">No speakers defined.</p>'}
                        </div>
                    </div>

                    <!-- Services Section -->
                    <div class="space-y-6">
                        <h2 class="text-3xl font-bold text-gray-900 border-b pb-2">${data.services_heading || '[Services Heading Missing]'}</h2>
                        <p class="text-gray-600">${data.services_subtext || '[Services Subtext Missing]'}</p>
                        ${servicesList}
                    </div>

                    <!-- Contact Section Labels -->
                    <div class="space-y-4 p-6 bg-yellow-50 rounded-xl border border-yellow-200">
                        <h2 class="text-2xl font-bold text-gray-900">${data.contact_heading || '[Contact Heading Missing]'}</h2>
                        <p class="text-gray-700">Form Fields: ${data.form_name || '[Name]'}, ${data.form_email || '[Email]'}</p>
                        <p class="text-gray-700">Submit Button: <span class="font-medium">${data.form_submit || '[Submit]'}</span></p>
                    </div>

                    <!-- Footer -->
                    <p class="text-center text-xs text-gray-400 pt-8 border-t">${data.footer_rights || 'Footer Rights Missing'}</p>
                </div>
            `;
        }

        function showPreviewModal() {
            const modal = $('#preview-modal');
            const content = $('#preview-content');
            const data = contentData[activeLanguage];

            content.innerHTML = renderPreviewModalContent(data);

            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        function viewJsonExport() {
            const data = contentData[activeLanguage];
            const jsonString = JSON.stringify(data, null, 2);

            const modal = $('#json-modal');
            $('#json-content').textContent = jsonString;

            // Show modal
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        function copyJsonToClipboard() {
            const jsonText = $('#json-content').textContent;
            
            // Use fallback method for clipboard access due to iframe restrictions
            const textarea = document.createElement('textarea');
            textarea.value = jsonText;
            document.body.appendChild(textarea);
            textarea.select();
            
            try {
                const successful = document.execCommand('copy');
                if (successful) {
                    showMessage('Copied!', `${activeLanguage.toUpperCase()}.json content copied to clipboard.`, 'success');
                } else {
                    throw new Error('Fallback copy failed.');
                }
            } catch (err) {
                showMessage('Error', 'Failed to copy to clipboard. Please copy manually from the window.', 'error');
            }
            
            document.body.removeChild(textarea);
            hideModal('json-modal');
        }


        // --- FORM SUBMISSION AND LISTENER SETUP ---

        function setupFormListeners(contentType, data) {
            if (contentType === 'Speaker Information') {
                $$('.speaker-edit-form').forEach(form => {
                    form.addEventListener('submit', handleSpeakerEdit);
                });
                $$('.delete-speaker-btn').forEach(btn => {
                    btn.addEventListener('click', handleSpeakerDeleteClick);
                });
                $('#add-speaker-form').addEventListener('submit', handleAddSpeaker);
            } else {
                $('#generic-form')?.addEventListener('submit', (e) => handleGenericSubmit(e, data));
            }
            
            // Listener for JSON copy button (must be set up after dashboard renders)
            $('#json-modal button.bg-indigo-500')?.addEventListener('click', copyJsonToClipboard);
        }

        function handleGenericSubmit(event, currentData) {
            event.preventDefault();
            const formData = new FormData(event.target);
            const newContent = { ...currentData };

            for (const [key, value] of formData.entries()) {
                // Update the key in the new content object
                newContent[key] = value.trim();
            }

            // Perform the update using localStorage
            saveContentToLocalStorage(activeLanguage, newContent);
        }

        function handleAddSpeaker(event) {
            event.preventDefault();
            const idInput = $('#new-speaker-id');
            const newId = idInput.value.trim().toLowerCase().replace(/\s+/g, '_').replace(/[^a-z0-9_]/g, '');

            if (!newId) {
                showMessage('Error', 'Speaker ID cannot be empty.', 'error');
                return;
            }

            if (contentData[activeLanguage].speakers && contentData[activeLanguage].speakers[newId]) {
                showMessage('Error', `Speaker ID '${newId}' already exists. Choose a unique ID.`, 'error');
                return;
            }

            const newSpeaker = {
                name: `New Speaker`,
                title: `New Role`,
                bio_long: `Detailed biography for ${newId}.`,
                focus: ["Topic 1", "Topic 2"],
                image_url: `https://placehold.co/100x100/3c3c3c/ffffff?text=${newId.toUpperCase().substring(0,2)}`
            };

            const updatedSpeakers = { ...contentData[activeLanguage].speakers, [newId]: newSpeaker };
            const newContent = { ...contentData[activeLanguage], speakers: updatedSpeakers };

            idInput.value = '';
            // Perform the update using localStorage
            saveContentToLocalStorage(activeLanguage, newContent);
        }

        function handleSpeakerEdit(event) {
            event.preventDefault();
            const form = event.target;
            const speakerId = form.dataset.speakerId;
            const formData = new FormData(form);

            const updatedSpeaker = { ...contentData[activeLanguage].speakers[speakerId] };

            for (const [key, value] of formData.entries()) {
                if (key === 'focus') {
                    // Split comma-separated string into an array of trimmed strings
                    updatedSpeaker[key] = value.split(',').map(s => s.trim()).filter(s => s.length > 0);
                } else {
                    updatedSpeaker[key] = value.trim();
                }
            }

            const updatedSpeakers = { ...contentData[activeLanguage].speakers, [speakerId]: updatedSpeaker };
            const newContent = { ...contentData[activeLanguage], speakers: updatedSpeakers };

            // Perform the update using localStorage
            saveContentToLocalStorage(activeLanguage, newContent);
        }
        
        // Custom Modal Confirmation for Deletion
        function handleSpeakerDeleteClick(event) {
            const speakerId = event.target.closest('button').dataset.speakerId;
            
            // Set message and show modal
            $('#delete-confirm-message').textContent = `Are you sure you want to delete the speaker with ID '${speakerId}'? This action cannot be undone.`;
            $('#delete-confirm-modal').classList.remove('hidden');
            $('#delete-confirm-modal').classList.add('flex');

            // Clear previous listener and attach new one
            const confirmBtn = $('#confirm-delete-btn');
            confirmBtn.replaceWith(confirmBtn.cloneNode(true));
            $('#confirm-delete-btn').addEventListener('click', () => {
                handleSpeakerDelete(speakerId);
            });
        }

        function handleSpeakerDelete(speakerId) {
            // This is the actual deletion logic called after confirmation
            const updatedSpeakers = { ...contentData[activeLanguage].speakers };
            delete updatedSpeakers[speakerId];

            const newContent = { ...contentData[activeLanguage], speakers: updatedSpeakers };
            
            // Perform the update using localStorage
            saveContentToLocalStorage(activeLanguage, newContent);
            
            hideModal('delete-confirm-modal');
            showMessage('Deleted', `Speaker '${speakerId}' has been deleted.`, 'error');
        }

        // --- INITIALIZATION AND MAIN RENDER LOOP ---

        function initializeApp() {
            // Load existing content from local storage or bootstrap initial content
            loadContentFromLocalStorage();

            // Check for simulated session state for better UX
            const localAuth = localStorage.getItem('admin_auth_status') === 'true';
            isAuthenticated = isAuthenticated || localAuth;

            render();
        }

        function render() {
            if (isAuthenticated) {
                renderAdminDashboard();
            } else {
                renderLoginForm();
            }
        }

        // Start the application
        initializeApp();
    </script>
</body>
</html>
