#include <Arduino.h>

// Пін для фоторезистора (ADC1)
const int ldrPin = 34;

// Змінні-прапорці для переривань таймерів
volatile bool timer0Flag = false;
volatile bool timer1Flag = false;

// Об'єкти таймерів
hw_timer_t *timer0 = NULL;
hw_timer_t *timer1 = NULL;

// --- Обробник першого таймера (ISR) ---
void IRAM_ATTR onTimer0() {
  timer0Flag = true;
}

// --- Обробник другого таймера (ISR) ---
void IRAM_ATTR onTimer1() {
  timer1Flag = true;
}

void setup() {
  Serial.begin(115200);
  delay(1000);
  Serial.println("--- ДОСЛІДЖЕННЯ ТАЙМЕРІВ ESP32 ---");

  // 1. Налаштування першого таймера (Період: 1 секунда)
  // Частота таймера ESP32 за замовчуванням 80МГц. 
  // timerBegin(частота_в_Гц)
  timer0 = timerBegin(1000000); // 1 МГц (1 мільйон тіків на секунду)
  timerAttachInterrupt(timer0, &onTimer0);
  // Спрацьовувати кожні 1 000 000 тіків (1 секунда), autoreload = true
  timerAlarm(timer0, 1000000, true, 0);

  // 2. Налаштування другого таймера (Період: 3.5 секунди)
  timer1 = timerBegin(1000000); 
  timerAttachInterrupt(timer1, &onTimer1);
  // Спрацьовувати кожні 3 500 000 тіків (3.5 секунди)
  timerAlarm(timer1, 3500000, true, 0);

  Serial.println("Таймери запущені:");
  Serial.println("Таймер 0: кожну 1.0 сек");
  Serial.println("Таймер 1: кожні 3.5 сек");
}

void loop() {
  // Обробка першого таймера
  if (timer0Flag) {
    int val = analogRead(ldrPin);
    Serial.print("[Таймер 0 (1с)]: Зчитування LDR = ");
    Serial.println(val);
    timer0Flag = false; // Скидаємо прапорець
  }

  // Обробка другого таймера
  if (timer1Flag) {
    int val = analogRead(ldrPin);
    Serial.print(">>> [Таймер 1 (3.5с)]: Важливе зчитування LDR = ");
    Serial.println(val);
    timer1Flag = false; // Скидаємо прапорець
  }
}
