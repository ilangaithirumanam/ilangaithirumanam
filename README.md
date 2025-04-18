<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>இலங்கை திருமணம் - Sri Lankan Matrimony</title>
    <style>
        /* Basic CSS Styling */
        body {
            font-family: sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            background-color: #f4f4f4;
            color: #333;
        }

        .container {
            max-width: 800px;
            margin: auto;
            background: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        h1, h2 {
            text-align: center;
            color: #5a2d82; /* Purple color */
            margin-bottom: 20px;
        }

        /* Form Styling */
        .form-section {
            margin-bottom: 30px;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 5px;
            background-color: #f9f9f9;
        }

        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }

        input[type="text"],
        input[type="tel"],
        input[type="email"], /* Added email just in case */
        input[type="date"],
        input[type="time"],
        input[type="number"],
        input[type="file"],
        select {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box; /* Ensures padding doesn't affect width */
        }

        button {
            display: block;
            width: 100%;
            padding: 12px;
            background-color: #5a2d82; /* Purple */
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #482469; /* Darker purple */
        }

        /* Hidden sections */
        #otp-section,
        #profile-details-section,
        #profile-display-section {
            display: none; /* Initially hidden */
        }

        /* Profile Display */
        #profiles-container {
            margin-top: 20px;
        }

        .profile-card {
            border: 1px solid #eee;
            background-color: #fff;
            padding: 15px;
            margin-bottom: 15px;
            border-radius: 5px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.05);
        }

        .profile-card h3 {
            margin-top: 0;
            margin-bottom: 10px;
            color: #5a2d82;
        }

        .profile-card p {
            margin: 5px 0;
        }

        .profile-card .hidden-info {
            color: #888;
            font-style: italic;
        }

        /* Image Preview */
        #photo-preview {
            margin-top: 10px;
            max-width: 150px;
            max-height: 150px;
            border: 1px solid #ddd;
            display: block; /* Initially hidden until image selected */
            margin-bottom: 15px;
        }
         #photo-preview:not(:empty) { /* Show border only if preview exists */
            padding: 5px;
         }


        /* Messages */
        .message {
            padding: 10px;
            margin-bottom: 15px;
            border-radius: 4px;
            text-align: center;
        }
        .error {
            background-color: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        .success {
             background-color: #d4edda;
             color: #155724;
             border: 1px solid #c3e6cb;
        }

    </style>
</head>
<body>

    <div class="container">
        <h1>இலங்கை திருமணம் - Sri Lankan Matrimony</h1>

        <!-- 1. Registration Section -->
        <div id="registration-section" class="form-section">
            <h2>Create Account (Step 1)</h2>
            <div id="reg-message" class="message" style="display: none;"></div>
            <form id="registration-form">
                <label for="reg-name">Name:</label>
                <input type="text" id="reg-name" name="name" required>

                <label for="reg-phone">Phone Number:</label>
                <input type="tel" id="reg-phone" name="phone" placeholder="e.g., 0771234567" required>
                <!-- Add pattern for basic validation if needed: pattern="[0-9]{10}" -->

                <button type="button" id="send-otp-btn">Send OTP</button>
            </form>
        </div>

        <!-- 2. OTP Verification Section -->
        <div id="otp-section" class="form-section">
            <h2>Verify Phone Number (Step 2)</h2>
             <p>An OTP has been sent to <strong id="otp-phone-display"></strong> (This is simulated).</p>
            <div id="otp-message" class="message" style="display: none;"></div>
            <form id="otp-form">
                <label for="otp-input">Enter OTP:</label>
                <input type="number" id="otp-input" name="otp" required>

                <button type="button" id="verify-otp-btn">Verify OTP</button>
            </form>
        </div>

        <!-- 3. Profile Details Section -->
        <div id="profile-details-section" class="form-section">
            <h2>Enter Your Details (Step 3)</h2>
            <div id="profile-message" class="message" style="display: none;"></div>
            <form id="profile-form">
                <label for="profile-photo">Photo:</label>
                <input type="file" id="profile-photo" name="photo" accept="image/*">
                <img id="photo-preview" src="#" alt="Photo Preview" style="display: none;"> <!-- Hidden until image is selected -->

                <label for="profile-name">Name:</label>
                <input type="text" id="profile-name" name="name" readonly required> <!-- Readonly, filled from step 1 -->

                <label for="profile-gender">Gender:</label>
                <select id="profile-gender" name="gender" required>
                    <option value="">Select Gender</option>
                    <option value="Male">Male</option>
                    <option value="Female">Female</option>
                    <option value="Other">Other</option>
                </select>

                <label for="profile-city">City / Town:</label>
                <input type="text" id="profile-city" name="city" required>

                <label for="profile-dob">Date of Birth:</label>
                <input type="date" id="profile-dob" name="dob" required>

                <label for="profile-tob">Time of Birth:</label>
                <input type="time" id="profile-tob" name="tob"> <!-- Not always required -->

                <label for="profile-profession">Profession:</label>
                <input type="text" id="profile-profession" name="profession" required>

                <label for="profile-caste">Caste:</label>
                <input type="text" id="profile-caste" name="caste" required>

                <label for="profile-phone">Phone Number:</label>
                <input type="tel" id="profile-phone" name="phone" readonly required> <!-- Readonly, filled from step 1 -->

                <button type="button" id="save-profile-btn">Create Profile</button>
            </form>
        </div>

        <!-- 4. Profile Display Section (For all users) -->
        <div id="profile-display-section" class="form-section">
            <h2>Registered Profiles</h2>
             <p><i>Note: Photo and Phone Number are hidden for privacy.</i></p>
            <div id="profiles-container">
                <!-- Profiles will be loaded here by JavaScript -->
                 <p>No profiles created yet.</p>
            </div>
        </div>

        <!-- Admin Note -->
        <div style="text-align: center; margin-top: 30px; font-size: 0.9em; color: #555;">
            <p><strong>Admin Note:</strong> This is a frontend prototype. Real user management, data storage, OTP functionality, and admin controls require a backend server and database.</p>
        </div>
    </div>

    <script>
        // --- DOM Elements ---
        const registrationSection = document.getElementById('registration-section');
        const otpSection = document.getElementById('otp-section');
        const profileDetailsSection = document.getElementById('profile-details-section');
        const profileDisplaySection = document.getElementById('profile-display-section');

        const regForm = document.getElementById('registration-form');
        const regNameInput = document.getElementById('reg-name');
        const regPhoneInput = document.getElementById('reg-phone');
        const sendOtpBtn = document.getElementById('send-otp-btn');
        const regMessage = document.getElementById('reg-message');


        const otpForm = document.getElementById('otp-form');
        const otpInput = document.getElementById('otp-input');
        const verifyOtpBtn = document.getElementById('verify-otp-btn');
        const otpPhoneDisplay = document.getElementById('otp-phone-display');
        const otpMessage = document.getElementById('otp-message');


        const profileForm = document.getElementById('profile-form');
        const profilePhotoInput = document.getElementById('profile-photo');
        const photoPreview = document.getElementById('photo-preview');
        const profileNameInput = document.getElementById('profile-name');
        const profileGenderInput = document.getElementById('profile-gender');
        const profileCityInput = document.getElementById('profile-city');
        const profileDobInput = document.getElementById('profile-dob');
        const profileTobInput = document.getElementById('profile-tob');
        const profileProfessionInput = document.getElementById('profile-profession');
        const profileCasteInput = document.getElementById('profile-caste');
        const profilePhoneInput = document.getElementById('profile-phone');
        const saveProfileBtn = document.getElementById('save-profile-btn');
        const profileMessage = document.getElementById('profile-message');


        const profilesContainer = document.getElementById('profiles-container');

        // --- State Variables ---
        let currentUserName = '';
        let currentUserPhone = '';
        let currentUserPhotoData = null; // Store file object or data URL for preview
        let registeredProfiles = []; // In-memory storage (replace with backend)

        // --- Functions ---

        function showMessage(element, message, isError = false) {
             element.textContent = message;
             element.className = isError ? 'message error' : 'message success';
             element.style.display = 'block';
        }

        function hideMessage(element) {
            element.style.display = 'none';
        }


        // Function to display profiles (hiding sensitive info)
        function renderProfiles() {
            profilesContainer.innerHTML = ''; // Clear previous profiles

            if (registeredProfiles.length === 0) {
                profilesContainer.innerHTML = '<p>No profiles created yet.</p>';
                profileDisplaySection.style.display = 'block'; // Show section even if empty
                return;
            }

            registeredProfiles.forEach(profile => {
                const card = document.createElement('div');
                card.className = 'profile-card';

                // Basic Info (Public)
                let cardHTML = `
                    <h3>${profile.name}</h3>
                    <p><strong>Gender:</strong> ${profile.gender}</p>
                    <p><strong>City:</strong> ${profile.city}</p>
                    <p><strong>Date of Birth:</strong> ${profile.dob}</p>
                    <p><strong>Time of Birth:</strong> ${profile.tob || 'N/A'}</p>
                    <p><strong>Profession:</strong> ${profile.profession}</p>
                    <p><strong>Caste:</strong> ${profile.caste}</p>
                `;

                // Add placeholders for hidden info
                cardHTML += `<p class="hidden-info"><strong>Photo:</strong> [Hidden]</p>`;
                cardHTML += `<p class="hidden-info"><strong>Phone:</strong> [Hidden]</p>`;

                card.innerHTML = cardHTML;
                profilesContainer.appendChild(card);
            });

            profileDisplaySection.style.display = 'block'; // Make sure display section is visible
        }

        // --- Event Listeners ---

        // 1. Send OTP Button
        sendOtpBtn.addEventListener('click', () => {
            hideMessage(regMessage);
            const name = regNameInput.value.trim();
            const phone = regPhoneInput.value.trim();

            if (!name || !phone) {
                 showMessage(regMessage, 'Please enter both Name and Phone Number.', true);
                return;
            }
             // Basic phone validation (example: Sri Lankan format - improve as needed)
             if (!/^(0\d{9})$/.test(phone)) {
                 showMessage(regMessage, 'Please enter a valid 10-digit Sri Lankan phone number (e.g., 0771234567).', true);
                 return;
             }


            // ** SIMULATE OTP SENDING **
            // In a real app, this would make an API call to your backend
            console.log(`Simulating OTP send to: ${phone} for user: ${name}`);
            // alert(`Simulated OTP sent to ${phone}. For testing, use OTP: 123456`); // Optional alert

            // Store details temporarily
            currentUserName = name;
            currentUserPhone = phone;

            // Update UI
             showMessage(regMessage, `Simulated OTP sent to ${phone}. Use '123456' to verify.`, false);
            otpPhoneDisplay.textContent = phone; // Show phone number in OTP section
            registrationSection.style.display = 'none'; // Hide registration
            otpSection.style.display = 'block';         // Show OTP section
            otpInput.value = ''; // Clear any previous OTP input
            otpInput.focus();
        });

        // 2. Verify OTP Button
        verifyOtpBtn.addEventListener('click', () => {
            hideMessage(otpMessage);
            const otp = otpInput.value.trim();

            if (!otp) {
                showMessage(otpMessage, 'Please enter the OTP.', true);
                return;
            }

            // ** SIMULATE OTP VERIFICATION **
            // In a real app, this would make an API call to verify the OTP
            // We'll use a hardcoded value for this demo
            const MOCK_OTP = "123456";

            if (otp === MOCK_OTP) {
                 showMessage(otpMessage, 'OTP Verified Successfully!', false);

                // Proceed to profile details
                profileNameInput.value = currentUserName; // Pre-fill name
                profilePhoneInput.value = currentUserPhone; // Pre-fill phone
                photoPreview.style.display = 'none'; // Hide preview initially
                photoPreview.src = '#'; // Reset preview source

                otpSection.style.display = 'none';             // Hide OTP section
                profileDetailsSection.style.display = 'block'; // Show Profile Details section
                profileForm.reset(); // Clear other fields (except pre-filled ones)
                profileNameInput.value = currentUserName; // Re-apply pre-filled name after reset
                profilePhoneInput.value = currentUserPhone; // Re-apply pre-filled phone after reset


            } else {
                showMessage(otpMessage, 'Invalid OTP. Please try again.', true);
                otpInput.focus();
            }
        });

        // 3. Photo Preview Handler
        profilePhotoInput.addEventListener('change', (event) => {
            const file = event.target.files[0];
            if (file && file.type.startsWith('image/')) {
                currentUserPhotoData = file; // Store the file object
                const reader = new FileReader();
                reader.onload = (e) => {
                    photoPreview.src = e.target.result;
                    photoPreview.style.display = 'block'; // Show the preview
                }
                reader.readAsDataURL(file);
            } else {
                // Clear preview if invalid file or no file selected
                 currentUserPhotoData = null;
                photoPreview.src = '#';
                photoPreview.style.display = 'none';
            }
        });


        // 4. Save Profile Button
        saveProfileBtn.addEventListener('click', () => {
             hideMessage(profileMessage);
            // Basic validation (add more as needed)
            if (!profileGenderInput.value || !profileCityInput.value.trim() || !profileDobInput.value || !profileProfessionInput.value.trim() || !profileCasteInput.value.trim()) {
                showMessage(profileMessage, 'Please fill in all required fields.', true);
                return;
            }

            // Create profile object (excluding photo file itself for this demo)
            const newProfile = {
                id: Date.now(), // Simple unique ID for demo
                name: profileNameInput.value,
                gender: profileGenderInput.value,
                city: profileCityInput.value.trim(),
                dob: profileDobInput.value,
                tob: profileTobInput.value || null, // Handle empty time
                profession: profileProfessionInput.value.trim(),
                caste: profileCasteInput.value.trim(),
                phone: profilePhoneInput.value, // Keep phone internally, but don't display publicly
                hasPhoto: !!currentUserPhotoData // Store whether a photo was uploaded
                // In a real app, you'd handle the photo upload to the backend here
            };

            // ** SIMULATE SAVING TO DATABASE **
            registeredProfiles.push(newProfile);
            console.log("Profile Saved (Simulated):", newProfile);
            console.log("All Profiles:", registeredProfiles);

            // Update UI
             showMessage(profileMessage, 'Profile created successfully!', false);
             setTimeout(() => { // Add a small delay before resetting and hiding
                 profileDetailsSection.style.display = 'none'; // Hide profile form
                 registrationSection.style.display = 'block';  // Show registration form again for new user
                 regForm.reset(); // Clear registration form
                 hideMessage(profileMessage); // Hide success message after showing reg section
             }, 1500); // 1.5 second delay


            // Render updated profile list
            renderProfiles();

            // Clear temporary variables
            currentUserName = '';
            currentUserPhone = '';
             currentUserPhotoData = null;
        });

        // --- Initial Setup ---
        // Ensure only the registration section is visible on load
        registrationSection.style.display = 'block';
        otpSection.style.display = 'none';
        profileDetailsSection.style.display = 'none';
        // Render any initially stored profiles (if any existed, though in this demo it starts empty)
        renderProfiles(); // This will show the "Registered Profiles" section title and the "No profiles" message initially

    </script>

</body>
</html>
