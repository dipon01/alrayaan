<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Al Rayyan Transportation, LLC</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
    <script type="module" src="https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js"></script>
    <script type="module" src="https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js"></script>
    <script type="module" src="https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js"></script>
    <style>
        html {
            scroll-behavior: smooth;
        }
        body {
            font-family: 'Inter', sans-serif;
            background-image: url('Orlando Downtown.jpeg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            background-repeat: no-repeat;
        }
        .form-input {
            width: 100%;
            padding: 12px;
            border-radius: 8px;
            border: 1px solid #d1d5db;
            outline: none;
            transition: border-color 0.2s;
            background-color: white;
        }
        .form-input:focus {
            border-color: #3b82f6;
        }
    </style>
</head>
<body>

    <!-- Header with Navigation -->
    <header id="top" class="bg-white/80 backdrop-blur-sm p-2 md:p-4 rounded-b-xl shadow-lg w-full sticky top-0 z-50">
      <div class="container mx-auto flex flex-col md:flex-row items-center justify-between">
        <h1 class="text-xl md:text-2xl font-bold text-gray-900 mb-2 md:mb-0">Al Rayyan Transportation, LLC</h1>
        <nav class="flex flex-wrap justify-center gap-2 mt-2 md:mt-0">
          <a href="#book-now" class="px-4 py-2 rounded-lg text-gray-400 font-medium hover:bg-gray-200 transition-colors duration-200">Home</a>
          <a href="#about" class="px-4 py-2 rounded-lg text-gray-400 font-medium hover:bg-gray-200 transition-colors duration-200">About</a>
          <a href="#fleet" class="px-4 py-2 rounded-lg text-gray-400 font-medium hover:bg-gray-200 transition-colors duration-200">My Vehicle</a>
          <a href="#rates" class="px-4 py-2 rounded-lg text-gray-400 font-medium hover:bg-gray-200 transition-colors duration-200">Rates</a>
        </nav>
      </div>
    </header>

    <!-- Book Now Section -->
    <section id="book-now" class="min-h-screen flex items-center justify-center py-16 px-4">
        <div class="container mx-auto max-w-2xl bg-white/80 backdrop-blur-sm rounded-xl p-8 shadow-2xl">
            <h2 class="text-5xl font-extrabold text-gray-900 text-center mb-4">Your Stress-Free Private Car Service</h2>
            <p class="text-gray-700 text-lg text-center mb-8">Arrive relaxed and ready for adventure. We offer seamless private transportation for families from Orlando to all major destinations.</p>
            
            <h3 class="text-3xl font-bold text-gray-900 text-center mb-6">Book Your Ride</h3>
            <form id="fareRequestForm" class="space-y-6">
                <div>
                    <label for="name" class="block text-sm font-medium text-gray-700">Your Full Name</label>
                    <input type="text" id="name" name="name" required class="mt-1 form-input">
                </div>
                <div>
                    <label for="email" class="block text-sm font-medium text-gray-700">Email Address</label>
                    <input type="email" id="email" name="email" required class="mt-1 form-input">
                </div>
                <div>
                    <label for="phone" class="block text-sm font-medium text-gray-700">Phone Number</label>
                    <input type="tel" id="phone" name="phone" required class="mt-1 form-input">
                </div>
                <div>
                    <label for="pickup" class="block text-sm font-medium text-gray-700">Pickup Location</label>
                    <input type="text" id="pickup" name="pickup" required class="mt-1 form-input">
                </div>
                <div>
                    <label for="dropoff" class="block text-sm font-medium text-gray-700">Drop-off Location</label>
                    <input type="text" id="dropoff" name="dropoff" required class="mt-1 form-input">
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div>
                        <label for="date" class="block text-sm font-medium text-gray-700">Date</label>
                        <input type="date" id="date" name="date" required class="mt-1 form-input">
                    </div>
                    <div>
                        <label for="time" class="block text-sm font-medium text-gray-700">Time</label>
                        <input type="time" id="time" name="time" required class="mt-1 form-input">
                    </div>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div>
                        <label for="passengers" class="block text-sm font-medium text-gray-700">Number of Passengers</label>
                        <input type="number" id="passengers" name="passengers" min="1" required class="mt-1 form-input">
                    </div>
                    <div>
                        <label for="luggage" class="block text-sm font-medium text-gray-700">Number of Luggage</label>
                        <input type="number" id="luggage" name="luggage" min="0" required class="mt-1 form-input">
                    </div>
                </div>
                <div id="messageBox" class="text-center text-sm font-medium text-gray-700"></div>
                <div>
                    <button type="submit" class="w-full bg-blue-600 text-white py-3 px-4 rounded-lg font-semibold hover:bg-blue-700 transition-colors duration-200 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2">
                        Request a Quote
                    </button>
                </div>
            </form>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-16 px-4 bg-gray-50">
        <div class="container mx-auto max-w-4xl text-center">
            <h2 class="text-4xl font-bold text-gray-900 mb-6">About Al Rayyan Transportation</h2>
            <p class="text-gray-700 text-lg leading-relaxed">
                Al Rayyan Transportation is your premier partner for reliable and comfortable private transportation in Central Florida. As the owner and sole operator, I am dedicated to providing a safe and stress-free experience for families and travelers in my top-of-the-line vehicle. My commitment to punctuality, professionalism, and impeccable customer service ensures your journey is as smooth as your destination. I believe that your travel experience should be effortless, which is why I offer transparent pricing and personalized service to meet your needs. Let me take the wheel while you sit back and enjoy the ride.
            </p>
        </div>
    </section>

    <!-- Our Fleet Section -->
    <section id="fleet" class="py-16 px-4 bg-gray-50">
        <div class="container mx-auto max-w-4xl">
            <h2 class="text-4xl font-bold text-gray-900 text-center mb-6">My Vehicle</h2>
            <p class="text-gray-700 text-lg text-center mb-8">
                Travel in comfort and style in my well-maintained vehicle.
            </p>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <img src="image6.jpeg" alt="Interior view of the van's last row" class="w-full h-auto rounded-xl shadow-md transform hover:scale-105 transition-transform duration-300 cursor-pointer" loading="lazy">
                <img src="image5.jpeg" alt="Interior view of the van's middle row" class="w-full h-auto rounded-xl shadow-md transform hover:scale-105 transition-transform duration-300 cursor-pointer" loading="lazy">
                <img src="image4.jpeg" alt="Interior view from the front passenger seat" class="w-full h-auto rounded-xl shadow-md transform hover:scale-105 transition-transform duration-300 cursor-pointer" loading="lazy">
                <img src="image3.jpeg" alt="Interior view of the dashboard and steering wheel" class="w-full h-auto rounded-xl shadow-md transform hover:scale-105 transition-transform duration-300 cursor-pointer" loading="lazy">
                <img src="image2.jpeg" alt="Rear view of the van" class="w-full h-auto rounded-xl shadow-md transform hover:scale-105 transition-transform duration-300 cursor-pointer" loading="lazy">
                <img src="image1.jpeg" alt="Front view of the van" class="w-full h-auto rounded-xl shadow-md transform hover:scale-105 transition-transform duration-300 cursor-pointer" loading="lazy">
                <img src="image0.jpeg" alt="Side view of the van" class="w-full h-auto rounded-xl shadow-md transform hover:scale-105 transition-transform duration-300 cursor-pointer" loading="lazy">
            </div>
        </div>
    </section>

    <!-- Rates Section -->
    <section id="rates" class="bg-white py-16 px-4">
        <div class="container mx-auto max-w-4xl">
            <h2 class="text-4xl font-bold text-gray-900 text-center mb-6">Al Rayyan Rate</h2>
            <div class="prose max-w-none text-center">
                <p>
                    Looking for premium Orlando transportation services? Al Rayyan Transportation offers a seamless and stress-free travel experience across Central Florida. We specialize in reliable Disney World transportation, hassle-free MCO airport transfers, and efficient Port Canaveral transportation, with tailored options for every need.
                </p>
                <p>
                    Our highly-rated transportation solutions prioritize your comfort, safety, and style, ensuring a smooth journey every time. Enjoy top-tier service without breaking the bank thanks to our affordable pricing.
                </p>
                <p>
                    Choose Al Rayyan Transportation for dependable, budget-friendly, and family-friendly travel services in Orlando. Experience the difference of a truly premium ride!
                </p>
            </div>
            <div class="mt-12 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 text-center">
                <!-- Orlando to WDW -->
                <div class="bg-gray-100 p-6 rounded-lg shadow-md">
                    <h4 class="text-xl font-bold text-gray-900 mb-2">Orlando International Airport to<br>Walt Disney World Resort Area</h4>
                    <ul class="mt-4 space-y-2">
                        <li>
                            <p class="text-lg font-medium text-gray-700">Al Rayyan Exclusive</p>
                            <p class="text-blue-600 font-bold">Starting at $60 Each Way</p>
                        </li>
                    </ul>
                </div>
                <!-- Orlando to Universal -->
                <div class="bg-gray-100 p-6 rounded-lg shadow-md">
                    <h4 class="text-xl font-bold text-gray-900 mb-2">Orlando International Airport to<br>Universal Orlando Resort Area</h4>
                    <ul class="mt-4 space-y-2">
                        <li>
                            <p class="text-lg font-medium text-gray-700">Al Rayyan Exclusive</p>
                            <p class="text-blue-600 font-bold">Starting at $50 Each Way</p>
                        </li>
                    </ul>
                </div>

                 <!-- MCO to Downtown Orlando -->
                <div class="bg-gray-100 p-6 rounded-lg shadow-md">
                    <h4 class="text-xl font-bold text-gray-900 mb-2">Orlando International Airport to<br>Downtown Orlando</h4>
                    <ul class="mt-4 space-y-2">
                        <li>
                            <p class="text-lg font-medium text-gray-700">Al Rayyan Exclusive</p>
                            <p class="text-blue-600 font-bold">Starting at $40 Each Way</p>
                        </li>
                    </ul>
                </div>

                 <!-- MCO to Champions Gate -->
                <div class="bg-gray-100 p-6 rounded-lg shadow-md">
                    <h4 class="text-xl font-bold text-gray-900 mb-2">Orlando International Airport to<br>Champions Gate</h4>
                    <ul class="mt-4 space-y-2">
                        <li>
                            <p class="text-lg font-medium text-gray-700">Al Rayyan Exclusive</p>
                            <p class="text-blue-600 font-bold">Starting at $75 Each Way</p>
                        </li>
                    </ul>
                </div>
                
                <!-- Orlando to Port Canaveral -->
                <div class="bg-gray-100 p-6 rounded-lg shadow-md">
                    <h4 class="text-xl font-bold text-gray-900 mb-2">Orlando International Airport to<br>Port Canaveral</h4>
                    <ul class="mt-4 space-y-2">
                        <li>
                            <p class="text-lg font-medium text-gray-700">Al Rayyan Exclusive</p>
                            <p class="text-blue-600 font-bold">Starting at $90 Each Way</p>
                        </li>
                    </ul>
                </div>
                <!-- WDW to Port Canaveral -->
                <div class="bg-gray-100 p-6 rounded-lg shadow-md">
                    <h4 class="text-xl font-bold text-gray-900 mb-2">Walt Disney World Resort Area to<br>Port Canaveral</h4>
                    <ul class="mt-4 space-y-2">
                        <li>
                            <p class="text-lg font-medium text-gray-700">Al Rayyan Exclusive</p>
                            <p class="text-blue-600 font-bold">Starting at $120 Each Way</p>
                        </li>
                    </ul>
                </div>

                 <!-- Disney to Sanford Internaltion -->
                <div class="bg-gray-100 p-6 rounded-lg shadow-md">
                    <h4 class="text-xl font-bold text-gray-900 mb-2">Disney to<br>Sanford International Airport</h4>
                    <ul class="mt-4 space-y-2">
                        <li>
                            <p class="text-lg font-medium text-gray-700">Al Rayyan Exclusive</p>
                            <p class="text-blue-600 font-bold">Starting at $90 Each Way</p>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-8">
        <div class="container mx-auto text-center">
            <p>&copy; 2024 Al Rayyan Transportation, LLC. All rights reserved.</p>
            <p class="text-sm mt-2">Designed and Developed by Al Rayyan Transportation</p>
        </div>
    </footer>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, signInWithCustomToken } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, collection, addDoc } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        // Global variables provided by the environment
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app-id';
        const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : {};
        const initialAuthToken = typeof __initial_auth_token !== 'undefined' ? __initial_auth_token : null;

        let db, auth;

        // Firebase Initialization
        const initFirebase = async () => {
            if (Object.keys(firebaseConfig).length === 0) {
                console.error("Firebase config is missing. Data will not be saved.");
                return;
            }
            try {
                const app = initializeApp(firebaseConfig);
                auth = getAuth(app);
                db = getFirestore(app);

                // Authenticate the user
                if (initialAuthToken) {
                    await signInWithCustomToken(auth, initialAuthToken);
                } else {
                    await signInAnonymously(auth);
                }
                console.log("Firebase initialized and authenticated.");
            } catch (error) {
                console.error("Error initializing Firebase:", error);
            }
        };

        // Call the initialization function
        initFirebase();

        const form = document.getElementById('fareRequestForm');
        const messageBox = document.getElementById('messageBox');

        form.addEventListener('submit', async (e) => {
            e.preventDefault();

            messageBox.textContent = "Processing your request...";
            messageBox.className = "text-center text-sm font-medium text-gray-500";
            
            // Get form data
            const formData = new FormData(form);
            const requestData = {
                customerName: formData.get('name'),
                email: formData.get('email'),
                phone: formData.get('phone'),
                pickupLocation: formData.get('pickup'),
                dropoffLocation: formData.get('dropoff'),
                date: formData.get('date'),
                time: formData.get('time'),
                passengers: formData.get('passengers'),
                luggage: formData.get('luggage'),
                timestamp: new Date()
            };

            if (!requestData.customerName || !requestData.email || !requestData.phone || !requestData.pickupLocation || !requestData.dropoffLocation || !requestData.date || !requestData.time || !requestData.passengers || !requestData.luggage) {
                messageBox.textContent = "Please fill out all required fields.";
                messageBox.className = "text-center text-sm font-medium text-red-500";
                return;
            }
            
            // Simulate sending an email
            console.log("Simulating email to driver with the following details:");
            console.log(requestData);

            // Save the request to Firestore
            if (db) {
                try {
                    const collectionPath = `/artifacts/${appId}/public/data/fare_requests`;
                    const docRef = await addDoc(collection(db, collectionPath), requestData);
                    console.log("Document successfully written with ID:", docRef.id);
                    messageBox.textContent = "Your fare request has been submitted and sent to our drivers. You will be contacted soon!";
                    messageBox.className = "text-center text-sm font-medium text-green-600";
                    form.reset();
                } catch (e) {
                    console.error("Error adding document:", e);
                    messageBox.textContent = "There was an error submitting your request. Please try again.";
                    messageBox.className = "text-center text-sm font-medium text-red-500";
                }
            } else {
                messageBox.textContent = "Firebase is not initialized. Data cannot be saved.";
                messageBox.className = "text-center text-sm font-medium text-red-500";
            }
        });
    </script>

</body>
</html>
