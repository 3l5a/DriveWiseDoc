Scrum et organisation / CDA analyse et conception : jeudi 28 mars > jeudi 4 avril
- MCD / modélisation
- setup du discord
- UML
- Maquette
- charte graphique
CDA Backend : vendredi 19 avril > vendredi 3 mai
- archi
CDA Frontend : jeudi 6 juin >  vendredi 14 juin
- CSS
- JS

22/04
- [x] Finir les modèles
- [x] Interfaces et signatures de méthodes dont on aura besoin
- [ ] Définition de nos DTO


# Interfaces
## Address

- [ ] Create
- [ ] Read : id, line1, line2, city
- [ ] Update : id, line1, line2, city
- [ ] Delete

## Brand
- [ ] Create (admin)
- [ ] Read : id, name
- [ ] Update (admin) : id, name
- [ ] Delete (admin)
- [ ] ReadAll (menu déroulant options) : id, name

## Carpool
- [ ] Create
- [ ] Read : id, endaddressid, startaddressid, dateid, vehicleid, driverid, passengers
- [ ] ReadAll (by...?) : id, endaddressid, startaddressid, dateid, vehicleid, driverid (dto collab : id, firstname, dto vehicle : url + category)
	- [ ] ReadByUser : idem (linq différent)
	- [ ] ReadByCity : idem idem
	- [ ] ReadByDate : idem idem
	- [ ] ReadByCityAndDate
- [ ] Update : id, endaddressid, startaddressid, dateid, vehicleid, driverid // attention modif impossible si passagers déjà réservés
- [ ] add passenger : id, passengers
- [ ] Delete
## Category
- [ ] Create (admin) : id, name
- [ ] Read :id, name
- [ ] Update (admin) :id, name
- [ ] Delete (admin)
- [ ] ReadAll (options menu) :id, name
## City
- [ ] Create : id, name, zipcode
- [ ] ReadById :id, name, zipcode
- [ ] StartsWith (recherche instantannée) : id, name, zipcode
- [ ] Update : id, name, zipcode
- [ ] Delete

## Collaborator
- [ ] Create
- [ ] Read (public profile) : id, firstname, lastname, addressid
- [ ] read (dashboard perso) : id, firstname, lastname, email, rentals, carpoolsasdriver, carpoolsaspassenger
- [ ] Update : id, firstname, lastname, email
- [ ] Delete (admin+user)
- [ ] GiveAdminRole (admin) : id/guid
- [ ] DeleteRole (admin)

## Role
- [ ] Create
- [ ] Update
- [ ] Delete
- [ ] ReadAll

## Date
- [ ] Create : id (date)

## Model
- [ ] Create (admin) : id, name
- [ ] Read : id, name
- [ ] ReadAll : id, name
- [ ] Update (admin) : id, name
- [ ] Delete (admin)
- [ ] ReadByBrand : id, name

## Motor
- [ ] Create (admin) : id, type
- [ ] Read : id, type
- [ ] ReadAll : id, type
- [ ] Update (admin) : id, type
- [ ] Delete (admin)

## Rental
- [ ] Create  : vehicleId, collaboratorId, StartDateId, EndDateId
- [ ] Update : verif pas de covoit + vérif dates ok : vehicleId, collaboratorId, StartDateId, EndDateId
- [ ] Read : vehicleId, collaboratorId, StartDateId, EndDateId
- [ ] ReadAll (?) : vehicleId, collaboratorId, StartDateId, EndDateId
	- [ ] ReadByUser : vehicleId, collaboratorId, StartDateId, EndDateId
	- [ ] ReadByDate : vehicleId, collaboratorId, StartDateId, EndDateId
	- [ ] ReadByUserAndDate : vehicleId, collaboratorId, StartDateId, EndDateId

## Status
- [ ] Create (admin) : id, name
- [ ] Read (admin) : id, name
- [ ] ReadAll (admin) : id, name
- [ ] Update : id, name
- [ ] Delete

## Vehicle
- [ ] Create (admin) : registration, totalseats, co2emissionkm, motorid, categoryId, ModelId
- [ ] ReadAdmin : + id, **statusid** : verif plages de réservations
- [ ] ReadCollab :  + id
- [ ] ReadAllCollab : verif dispo : +id
	- [ ] ReadAllAdmin : +id, **statusid**
- [ ] Update (admin) :  +id, **statusid**
- [ ] UpdateStatus : +id, statusId
- [ ] Delete (admin)
- [ ] ReadBy :
	- [ ] Status (admin) : +id, **statusid**
	- [ ] Model : +id
		- [ ] ModelAdmin : +id, **statusid**
	- [ ] Brand : +id
		- [ ] BrandAdmin : +id, **statusid**
	- [ ] Motor.Type : +id
		- [ ] MotorTypeAdmin : +id, **statusid**
	- [ ] Category : +id
		- [ ] CategoryAdmin : +id, **statusid**
	- [ ] Address : +id
		- [ ] AddressAdmin : +id, **statusid**