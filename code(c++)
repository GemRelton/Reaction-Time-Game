#define LED_PIN 9
#define BUTTON_PIN 2

unsigned long startTime, reactionTime;
bool gameReady = false;

void setup() {
    pinMode(LED_PIN, OUTPUT);
    pinMode(BUTTON_PIN, INPUT_PULLUP);
    Serial.begin(9600);
    Serial.println("Press the button to start...");
}

void loop() {
    if (!gameReady) {
        while (digitalRead(BUTTON_PIN) == HIGH);  // Wait for button press
        Serial.println("Get Ready...");
        delay(random(1000, 5000));  // Random delay between 1s to 5s

        digitalWrite(LED_PIN, HIGH);
        startTime = millis();  // Start time tracking
        gameReady = true;
    }

    if (gameReady && digitalRead(BUTTON_PIN) == LOW) {
        reactionTime = millis() - startTime;  // Calculate reaction time
        Serial.print("Reaction Time: ");
        Serial.print(reactionTime);
        Serial.println(" ms");
        
        digitalWrite(LED_PIN, LOW);
        gameReady = false;  // Reset game state
        Serial.println("Press the button to start again...");
    }
}
