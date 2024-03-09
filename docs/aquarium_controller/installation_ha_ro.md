---
layout: default
title: Instalare HA (ro)
parent: Aquarium Controller
nav_order: 1
# grand_parent: Products
---

# Utilizati pagina aceasta pentru a configura dispozitivul Aquarium Controller in Home Assistant.

Toate dispozitivele contin softul preinstlat.
{: .highlight }

{: .note-title }
> ## Cerinte prealabile:
>
> Trebuie sa aveti Integrarea ESPHome preinstalata in Home Assistant.

Dupa conectarea dispozitivul la o sursa de curent de 12v cu alimentatorul din pachet, acesta o sa fie vizibil ca si o retea WiFi.

Dupa conectarea dispozitivul la o sursa de curent de 12v cu alimentatorul din pachet, acesta o sa fie vizibil ca si o retea WiFi.

1. Puteti sa folositi orice laptop, calculator (care are WiFi) sau telefon pentru a va conecta la dispozitiv, efectuand setarile necesare dispozitivului pentru conectarea la reteaua WiFi locala.
Deoarece dispozitivul foloseste un cip ESP32, doar retele WiFi pe 2.4 GHz o sa fie disponibile pentru conectare. 
Recomandam evitarea folosirii retelelor combinate de 2.5 GHz si 5 GHz, pentru a exclude ulterioare probleme de conexiunea.

	![](/docs/aquarium_controller/images/installation/controller_wifi.jpeg)

	{: .note}
	> ##### Nume dispozitiv: aquarium_controller-p1-mac_of_the_device
	

2. Dupa conectarea la dispozitiv, o sa fiti redirectionati in pagina cu setarile pentru conexiunea la reteaua WiFi locala.
		
	{: .note}
	> #####	NOTA: Daca nu s-a facut redirectionarea la pagina de conectare a dispozitivului, in orice browser (Edge, Chrome, FireFox) tastati adresa: http://192.168.4.1

	![](/docs/aquarium_controller/images/installation/login.jpeg)

3. Odata conectat la dispozitiv utilizati 
	Username:  (cel de pe dispozitiv)
	Password: (ce-a de de pe dispozitiv)) pentru a va conecta la dispozitiv

4. Dupa ce ati selectat reteaua WiFi si ati introdus parola, dispozitivul o sa se conecteze la reteaua dumneavoastra locala.

	![](/docs/aquarium_controller/images/installation/network_save.jpeg)	
