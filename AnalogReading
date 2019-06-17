#define sL A4
#define sR A5
#define IN1 A0
#define IN2 A1
#define IN3 A2
#define IN4 A3
#define Speedleft 5
#define Speedright 6
#define ledBL 12
#define ledBR 7
#define ledRL 11
#define ledRR 10
#define line 500
#define s0 0
#define s1 10
#define s2 130
#define s3 255
#define DELAY 100
int left;
int right;

// Funções para ativação dos motores:
// leftCW, leftCCW, leftNEUTRAL, leftBRAKE
// rightCW, rightCCW, rightNEUTRAL, rightBRAKE

void setup() {
  pinMode(sR, INPUT);
  pinMode(sL, INPUT);
  pinMode(IN1, OUTPUT);
  pinMode(IN2, OUTPUT);
  pinMode(IN3, OUTPUT);
  pinMode(IN4, OUTPUT);
  pinMode(Speedleft, OUTPUT);
  pinMode(Speedright, OUTPUT);
  pinMode(ledBL, OUTPUT);
  pinMode(ledBR, OUTPUT);
  pinMode(ledRL, OUTPUT);
  pinMode(ledRR, OUTPUT);
  delay(3000);
  leftCCW();
  rightCW();
  analogWrite(Speedleft, s2);
  analogWrite(Speedright, s2);
  digitalWrite(ledBL, LOW);
  digitalWrite(ledBR, LOW);
  digitalWrite(ledRL, LOW);
  digitalWrite(ledRR, LOW);
}

void loop() {
  left = analogRead(sL);
  right = analogRead(sR);
  if (left < line && right < line) {
    leftCCW();
    rightCW();
    analogWrite(Speedleft, s2);
    analogWrite(Speedright, s2);
    delay(DELAY);
  }
  if (left < line && right > line) {
    leftCCW();
    rightCCW();
    analogWrite(Speedleft, s1);
    analogWrite(Speedright, s2);
    delay(DELAY);
  }
  if (left > line && right < line) {
    leftCW();
    rightCW();
    analogWrite(Speedleft, s2);
    analogWrite(Speedright, s1);
    delay(DELAY);
  }
  if (left > line && right > line) {
    leftCW();
    rightCW();
    analogWrite(Speedleft, s1);
    analogWrite(Speedright, s2);
    delay(DELAY);
  }
  leftBRAKE();
  rightBRAKE();
  analogWrite(Speedleft, s3);
  analogWrite(Speedright, s3);
  delay(80);
}

void rightCW() {
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, LOW);
}

void rightCCW() {
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, HIGH);
}

void rightNEUTRAL() {
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, LOW);
}

void rightBRAKE() {
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, HIGH);
}

void leftCW() {
  digitalWrite(IN3, HIGH);
  digitalWrite(IN4, LOW);
}

void leftCCW() {
  digitalWrite(IN3, LOW);
  digitalWrite(IN4, HIGH);
}

void leftNEUTRAL() {
  digitalWrite(IN3, LOW);
  digitalWrite(IN4, LOW);
}

void leftBRAKE() {
  digitalWrite(IN3, HIGH);
  digitalWrite(IN4, HIGH);
}
