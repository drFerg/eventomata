Events
======
1) E1 => A1
 - Event E1 causes Action A1
2) E1 -> E2 => A1
 - E1 followed by E2
3) E2 | E3 => A2
 - E2 or E3 
4) (E2 | E3) -> E1 => A3
 - E2 or E3 followed by E1
5) E1 -> E2[10s] => A4
 - E1 followed by E2 within 10s
6) E1 -> !E3 -> E2 => A5
 - E1 followed by E2 with no E3 inbetween
7) E1 & E2 => A6
 - E1 & E2 occur, irrespective of order

 temp.val > 23 => Notify('Too Hot')
 temp.val < 10 [10s] => Notify('Too Cold')
 temp.val > Avg => temp.mote.Cool()
 
 temp.val > 23 & weather.temp >23 => {
 	Notify('hot day');
 	airCon.turnOn();
 }

 presence.room == 'Bedroom' -> light.room == 'Bedroom' => Heat('Bedroom')

 sendPacket.mote == 1 -> recvPacket.mote == 5 => Notify('Packet success')

 (send.Packet.mote == 1 -> recvPacket.mote == 5) ! recvPacket.mote == 6 => Notify('Packet avoided 6')