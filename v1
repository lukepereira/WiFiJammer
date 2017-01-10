#include <ESP8266WiFi.h>
#include <WiFiUdp.h>

uint8_t pkt[1000];

void setup() {
  Serial.begin(115200);

  WiFi.mode(WIFI_AP);
  WiFi.softAP("00000000", "00000000", 6, 1);

  memset(pkt, 0, sizeof(pkt));
}

void loop() {
  WiFiUDP udp;
  udp.beginPacketMulticast(WiFi.softAPIP(), 1, IPAddress(255,255,255,255), 1);
  udp.write(pkt, sizeof(pkt));
  udp.endPacket();
}
