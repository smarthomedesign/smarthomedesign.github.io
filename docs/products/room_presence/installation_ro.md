---
layout: default
title: Instalare (ro)
parent: Room Presence
nav_order: 2
grand_parent: Products
---

# Utilizati pagina aceasta pentru a configura dispozitivul Room Presence in Home Assistant.

Toate dispozitivele contin softul preinstlat.
{: .highlight }

{: .note-title }
> ## Cerinte prealabile:
>
> Trebuie sa aveti Integrarea ESPHome preinstalata in Home Assistant.

In momentul in care conectati dispozitivul la o sursa de curent de 5v cu cablul MicroUSB sau folosind pinii de pe placa (5v si ground - pinii nu sunt conectati pe placa, trebuie lipiti ulterior), dispozitivul o sa fie vizibil ca si o retea WiFi.

1. Puteti sa folositi orice laptop, calculator (care are WiFi) sau telefon pentru a va conecta la dispozitiv si sa-i faceti setarile necesare pentru a se conecta la reteaua WiFi.
Deoarece dispozitivul foloseste un cip ESP32 doar reletele WiFi pe 2.4 GHz WiFi o sa fie disponibile pentru conectare. 
Va rog sa evitati sa folositi retele combinate de 2.5 GHz si 5 GHz pentru a nu avea probleme cu conexiunea.

	![image](./images/installation/device_wifi.png)

	{: .note}
	> ##### Nume dispozitiv: shd-room-presence-mac_of_the_device
	> ##### Daca aveti mai multe dispozitive, recomandarea este sa le conectati unul cate unul pentru a nu le pierde ordinea, care in ce camera este situat.

2. Odata conectati la dispozitiv o sa fiti redirectionati la pagina pentru a seta conexiunea dispozitivului in reteaua locala.

	![image](./images/installation/device_wifi_selection.png)

	Dupa ce ati selectat reteaua WiFi si ati introdus parola dispozitivului o sa se conecteze la reteaua dumneavoastra.

3. Daca dispozitivul s-a conectat cu succes la reteaua WiFi o sa devina vizibil in Home Assistance. 
	O sa apara o notificare:
	
	![image](./images/installation/ha_notification.png)

	{: .note}
	> Daca timp de 30 secunde dispozitivul nu apare in  Home Assistance incercati sa restartati dispozitivul sau verificati setarile retelei WiFi (vedeti saterile din router)
	> 
	> Daca dispozitivul nu este vizibil dupa restart incercati sa restartati Home Assistant.
	> 
	> Daca tot nu esti vizibil dupa (pasul 3) sau nu apare notificarea incercati (pasul 4)

4. In Home Assistant mergeti la: 
	### Settings - Devices & Services 
	si ar trebui sa vedeti dispozitivul:

	![image](./images/installation/devices_list.png)

5. Accesati CONFIGURE
	
	![image](./images/installation/configuration_confirmation.png)

6. Daca configurarea este cu succes o sa primiti o notificare in care puteti selecta locul in care o sa fie pus dispozitivul  (camera)

	![image](./images/installation/configuration_area.png)

7. Dupa ce selectati camera dispozitivul o sa fie vizibil in Integrarea ESPHome (il puteti cauta dupa nume)
	
	![image](./images/installation/esphome_devices.png)

8. Selectatti dispozitivul care tocmai l-ai instalat

	![image](./images/installation/device_entities.png)

9. Dupa ce selectati dispozitivul o sa aveti o lista cu toti senzorii disponibili in Home Assistant cu numele: default_room
	
	![image](./images/installation/device_sensors.png)

8. Ca sa schimbati numele camerei aveti doua optiuni:
	
	1. Recomandata: In ESPHome o sa apara un nou dispozitiv cu optiunea de ADOPT.
		
		![image](./images/installation/adopt_device.png)
	
	2. Puteti sa editati numele dispozitivului si id-ul fiecarei entitati.
		
	
9. Dupa ce dispozitivul este instalat (ADOPTED) in ESPHome puteti sa vedeti codul yaml
	
	![image](./images/installation/default_yaml.png)

10. Adaugati substitutile urmatoare in cod (dupa randul 2 in yaml):
	
	````markdown 
	room: "Bedroom" # replace this with your room name
	  temperature_offset: "-11.5"
	  humidity_offset: "0"
	  illuminance_offset: "-10"
	  temperature_update_interval: "20s"
	  illuminance_update_interval: "20s"
	  pir_delay_off: "30s"
	  occupancy_delay_off: "60s"
	```` 
	Aici puteti gasi intregul cod yaml pentru dispozitiv [here](https://github.com/smarthomedesign/room_presence/blob/main/room_presence.yaml)

11. Modificati numele camerei cu propriul vostru nume

	![image](./images/installation/yaml_with_offsets.png)

12. Instalati noul soft

13. Dupa ce instalarea este completa in Home Assistant navigati la 
	Settings - Devices & Services si Integrarea ESPHome selectand dispozitivul o sa observati ca toate entitatiile contin numele introdus
	
	![image](./images/installation/doubled_sensors.png)

14. O sa va apara entitatiile duplicate: default_room_<sensor_name> sunt entitatiile inactive. 
	Dupa un restart la Home Assistant o sa puteti sterge entitatiile respective.
