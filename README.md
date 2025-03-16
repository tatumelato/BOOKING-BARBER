<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Classic Cuts Barber Shop - Book Appointment</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #121212;
            color: #f1f1f1;
        }
        
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .logo {
            font-size: 32px;
            font-weight: bold;
            color: #ff1a1a;
            margin-bottom: 10px;
        }
        
        h1 {
            font-size: 24px;
            margin-bottom: 5px;
        }
        
        .subtitle {
            color: #bbbbbb;
            font-size: 16px;
        }
        
        .booking-form {
            background-color: #1e1e1e;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }
        
        input[type="text"],
        input[type="tel"],
        input[type="email"],
        input[type="date"],
        input[type="time"],
        select {
            width: 100%;
            padding: 12px;
            border: 1px solid #333;
            border-radius: 4px;
            background-color: #252525;
            color: #ffffff;
            font-size: 16px;
        }
        
        input:focus,
        select:focus {
            outline: none;
            border-color: #ff1a1a;
        }
        
        .tab-container {
            margin-bottom: 15px;
        }
        
        .tab-buttons {
            display: flex;
            margin-bottom: 15px;
        }
        
        .tab-button {
            flex: 1;
            padding: 10px;
            text-align: center;
            background-color: #252525;
            border: none;
            color: #ffffff;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .tab-button:first-child {
            border-top-left-radius: 4px;
            border-bottom-left-radius: 4px;
        }
        
        .tab-button:last-child {
            border-top-right-radius: 4px;
            border-bottom-right-radius: 4px;
        }
        
        .tab-button.active {
            background-color: #ff1a1a;
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        .haircut-options {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-top: 10px;
        }
        
        .haircut-option {
            border: 1px solid #333;
            border-radius: 6px;
            padding: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .haircut-option:hover {
            border-color: #ff1a1a;
        }
        
        .haircut-option.selected {
            background-color: rgba(255, 26, 26, 0.2);
            border-color: #ff1a1a;
        }
        
        .haircut-name {
            font-weight: bold;
            margin-bottom: 5px;
        }
        
        .haircut-price {
            color: #ff1a1a;
        }
        
        .radio-group {
            display: flex;
            gap: 20px;
            margin-top: 10px;
        }
        
        .radio-option {
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        button {
            background-color: #ff1a1a;
            color: white;
            border: none;
            padding: 15px 25px;
            font-size: 16px;
            font-weight: bold;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
            transition: background-color 0.3s ease;
        }
        
        button:hover {
            background-color: #e60000;
        }
        
        .footer {
            text-align: center;
            margin-top: 30px;
            color: #777;
        }
        
        .booking-number {
            text-align: center;
            padding: 15px;
            background-color: #252525;
            border-radius: 4px;
            margin-bottom: 20px;
            font-size: 18px;
            font-weight: bold;
            letter-spacing: 1px;
        }
        
        .booking-number span {
            color: #ff1a1a;
        }
        
        @media (max-width: 600px) {
            .haircut-options {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="logo">CLASSIC CUTS</div>
            <h1>Book Your Appointment</h1>
            <p class="subtitle">Look sharp, feel confident</p>
        </div>
        
        <div class="booking-form">
            <div class="booking-number">
                Booking #: <span id="bookingNumber">BC-25031601</span>
            </div>
            
            <form id="appointmentForm">
                <div class="form-group">
                    <label for="name">Your Name</label>
                    <input type="text" id="name" name="name" required>
                </div>
                
                <div class="form-group">
                    <label for="phone">Phone Number</label>
                    <input type="tel" id="phone" name="phone" required>
                </div>
                
                <div class="form-group">
                    <label for="email">Email (Optional)</label>
                    <input type="email" id="email" name="email">
                </div>
                
                <div class="form-group">
                    <label>Client Type</label>
                    <div class="tab-buttons">
                        <button type="button" class="tab-button active" data-tab="adults">Adults</button>
                        <button type="button" class="tab-button" data-tab="kids">Kids U/14</button>
                    </div>
                    
                    <div class="tab-container">
                        <div class="tab-content active" id="adults-tab">
                            <div class="haircut-options">
                                <div class="haircut-option" data-name="Brush Cut" data-price="70">
                                    <div class="haircut-name">Brush Cut</div>
                                    <div class="haircut-price">R70</div>
                                </div>
                                <div class="haircut-option" data-name="Normal Fade" data-price="80">
                                    <div class="haircut-name">Normal Fade</div>
                                    <div class="haircut-price">R80</div>
                                </div>
                                <div class="haircut-option" data-name="Fade with Dye" data-price="100">
                                    <div class="haircut-name">Fade with Dye</div>
                                    <div class="haircut-price">R100</div>
                                </div>
                                <div class="haircut-option" data-name="Bald Cut" data-price="30">
                                    <div class="haircut-name">Bald Cut</div>
                                    <div class="haircut-price">R30</div>
                                </div>
                                <div class="haircut-option" data-name="Normal Trim" data-price="10">
                                    <div class="haircut-name">Normal Trim</div>
                                    <div class="haircut-price">R10</div>
                                </div>
                                <div class="haircut-option" data-name="Dye Trim" data-price="20">
                                    <div class="haircut-name">Dye Trim</div>
                                    <div class="haircut-price">R20</div>
                                </div>
                                <div class="haircut-option" data-name="Style Fade" data-price="120">
                                    <div class="haircut-name">Style Fade</div>
                                    <div class="haircut-price">R120</div>
                                </div>
                            </div>
                        </div>
                        
                        <div class="tab-content" id="kids-tab">
                            <div class="haircut-options">
                                <div class="haircut-option" data-name="Brush Cut (Kids)" data-price="40">
                                    <div class="haircut-name">Brush Cut</div>
                                    <div class="haircut-price">R40</div>
                                </div>
                                <div class="haircut-option" data-name="Normal Fade (Kids)" data-price="60">
                                    <div class="haircut-name">Normal Fade</div>
                                    <div class="haircut-price">R60</div>
                                </div>
                                <div class="haircut-option" data-name="Fade with Dye (Kids)" data-price="80">
                                    <div class="haircut-name">Fade with Dye</div>
                                    <div class="haircut-price">R80</div>
                                </div>
                                <div class="haircut-option" data-name="Bald Cut (Kids)" data-price="20">
                                    <div class="haircut-name">Bald Cut</div>
                                    <div class="haircut-price">R20</div>
                                </div>
                                <div class="haircut-option" data-name="Normal Trim (Kids)" data-price="10">
                                    <div class="haircut-name">Normal Trim</div>
                                    <div class="haircut-price">R10</div>
                                </div>
                                <div class="haircut-option" data-name="Dye Trim (Kids)" data-price="20">
                                    <div class="haircut-name">Dye Trim</div>
                                    <div class="haircut-price">R20</div>
                                </div>
                                <div class="haircut-option" data-name="Style Fade (Kids)" data-price="100">
                                    <div class="haircut-name">Style Fade</div>
                                    <div class="haircut-price">R100</div>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <input type="hidden" id="selectedHaircut" name="selectedHaircut" required>
                    <input type="hidden" id="selectedPrice" name="selectedPrice" required>
                    <input type="hidden" id="clientType" name="clientType" value="Adult" required>
                </div>
                
                <div class="form-group">
                    <label for="date">Appointment Date</label>
                    <input type="date" id="date" name="date" required>
                </div>
                
                <div class="form-group">
                    <label for="time">Appointment Time</label>
                    <input type="time" id="time" name="time" required>
                </div>
                
                <div class="form-group">
                    <label>Payment Method</label>
                    <div class="radio-group">
                        <div class="radio-option">
                            <input type="radio" id="cash" name="payment" value="Cash" required>
                            <label for="cash">Cash</label>
                        </div>
                        <div class="radio-option">
                            <input type="radio" id="card" name="payment" value="Card">
                            <label for="card">Card</label>
                        </div>
                    </div>
                </div>
                
                <button type="submit" id="bookButton">Book Appointment</button>
            </form>
        </div>
        
        <div class="footer">
            <p>© 2025 Classic Cuts Barber Shop. All rights reserved.</p>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Generate random booking number
            const generateBookingNumber = () => {
                const date = new Date();
                const year = date.getFullYear().toString().substr(-2);
                const month = String(date.getMonth() + 1).padStart(2, '0');
                const day = String(date.getDate()).padStart(2, '0');
                const random = Math.floor(Math.random() * 1000).toString().padStart(3, '0');
                return `BC-${year}${month}${day}${random}`;
            };
            
            document.getElementById('bookingNumber').textContent = generateBookingNumber();
            
            // Set default date to today
            const today = new Date();
            const formattedDate = today.toISOString().split('T')[0];
            document.getElementById('date').setAttribute('min', formattedDate);
            
            // Tab switching for adult/kids
            const tabButtons = document.querySelectorAll('.tab-button');
            const tabContents = document.querySelectorAll('.tab-content');
            
            tabButtons.forEach(button => {
                button.addEventListener('click', function() {
                    // Update button states
                    tabButtons.forEach(btn => btn.classList.remove('active'));
                    this.classList.add('active');
                    
                    // Show the correct tab content
                    const tabId = this.getAttribute('data-tab');
                    tabContents.forEach(content => content.classList.remove('active'));
                    document.getElementById(`${tabId}-tab`).classList.add('active');
                    
                    // Update client type field
                    document.getElementById('clientType').value = tabId === 'adults' ? 'Adult' : 'Kid';
                    
                    // Reset haircut selection
                    document.querySelectorAll('.haircut-option').forEach(opt => opt.classList.remove('selected'));
                    document.getElementById('selectedHaircut').value = '';
                    document.getElementById('selectedPrice').value = '';
                });
            });
            
            // Haircut selection
            const haircutOptions = document.querySelectorAll('.haircut-option');
            haircutOptions.forEach(option => {
                option.addEventListener('click', function() {
                    // Remove selected class from all options in the same tab
                    const parentTab = this.closest('.tab-content');
                    parentTab.querySelectorAll('.haircut-option').forEach(opt => opt.classList.remove('selected'));
