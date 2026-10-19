🚦 Arduino PIR Motion Detection System
📌 Opis projektu

Projekt oparty na Arduino UNO, czterech czujnikach ruchu PIR oraz ośmiu diodach LED. System wykrywa ruch w czterech różnych strefach i steruje sygnalizacją świetlną.

W stanie spoczynku wszystkie diody świecą na czerwono. Po wykryciu ruchu przez jeden z czujników odpowiednia dioda zmienia kolor na zielony na 5 sekund.

Jeśli w tym czasie inny czujnik wykryje ruch, jego zgłoszenie zostaje zapisane w kolejce. Następne zielone światło włączy się po zakończeniu aktualnego cyklu.

🛠️ Wykorzystane komponenty
Arduino UNO
4 × czujnik ruchu PIR, np. HC-SR501
4 × czerwona dioda LED
4 × zielona dioda LED
8 × rezystor 220–330 Ω
Płytka stykowa
Przewody połączeniowe
Kabel USB
🔌 Schemat połączeń
Element	Pin Arduino
Czerwona dioda 1	D2
Zielona dioda 1	D3
Czerwona dioda 2	D4
Zielona dioda 2	D5
Czerwona dioda 3	D6
Zielona dioda 3	D7
Czerwona dioda 4	D8
Zielona dioda 4	D9
Czujnik PIR 1 (OUT)	D10
Czujnik PIR 2 (OUT)	D11
Czujnik PIR 3 (OUT)	D12
Czujnik PIR 4 (OUT)	D13
Zasilanie

Każdy czujnik PIR należy podłączyć zgodnie z jego dokumentacją:

VCC – odpowiednie napięcie zasilania.
GND – masa Arduino.
OUT – przypisany pin cyfrowy.

Każda dioda LED powinna mieć osobny rezystor ograniczający prąd. Wszystkie elementy muszą mieć wspólną masę.

⚙️ Jak działa system?
Po uruchomieniu wszystkie diody świecą na czerwono.
Czujniki PIR stale monitorują przypisane im strefy.
Wykrycie nowego ruchu powoduje dodanie zgłoszenia do kolejki.
System włącza zieloną diodę odpowiadającą pierwszemu zgłoszeniu.
Zielona dioda świeci przez 5 sekund.
Po upływie tego czasu system przełącza się na kolejne oczekujące zgłoszenie.
Jeżeli nie ma kolejnych zgłoszeń, wszystkie diody wracają do czerwonego koloru.
⏱️ Kolejka zgłoszeń

System wykorzystuje kolejkę o pojemności 20 oczekujących zgłoszeń.

Zgłoszenia są obsługiwane w kolejności ich wykrycia.
Każdy czujnik może mieć maksymalnie jedno oczekujące zgłoszenie.
Kolejne zgłoszenia są sprawdzane podczas trwania 5-sekundowego cyklu.
Zielone światło nie włącza się jednocześnie dla kilku czujników.
💻 Technologie
C++
Arduino IDE
Arduino UNO
Czujniki PIR
Diody LED
Funkcja millis() do odmierzania czasu bez blokowania programu
Tablica i kolejka do obsługi zgłoszeń

Projekt nie wymaga dodatkowych bibliotek.

🚀 Uruchomienie
Podłącz elementy zgodnie z tabelą połączeń.
Otwórz Arduino IDE.
Wklej kod do nowego szkicu.
Wybierz płytkę Arduino UNO.
Wybierz odpowiedni port.
Wgraj program na płytkę.
Poczekaj na inicjalizację czujników PIR i sprawdź działanie układu.
📂 Struktura repozytorium
arduino-pir-motion-system/
├── README.md
├── pir_led_system.ino
└── images/
    └── circuit.png


Zdjęcie układu możesz umieścić w folderze images, a następnie wyświetlić je w README:

![Schemat układu](images/circuit.png)

🔮 Możliwe rozszerzenia
Dodanie wyświetlacza LCD do prezentowania aktywnej strefy.
Dodanie buzzera sygnalizującego wykrycie ruchu.
Zmiana czasu świecenia zielonej diody.
Rozbudowa kolejki zgłoszeń.
Rejestrowanie zdarzeń przez port szeregowy.
Dodanie większej liczby czujników.
📄 Licencja

Projekt edukacyjny. Można go rozwijać, modyfikować i wykorzystywać do nauki programowania Arduino.

Autor: [Twój nick na GitHubie]

Projekt: Arduino PIR Motion Detection System

Platforma: Arduino UNO
