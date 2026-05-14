# Diccionario de datos – ASRS (Aviation Safety Reporting System)

Fuente: ASRS Coding Form (abril 2024). El ASRS es un sistema de reporte voluntario de seguridad aérea administrado por la NASA. Este diccionario describe las variables utilizadas en el formulario de codificación de reportes.

---

## Base de datos 1: Tiempo y Lugar

Información temporal y geográfica del evento reportado.

| Variable | Descripción | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --- | --- | --- | --- | --- |
| Date | Fecha del evento | Numérico (AAAAMM) | Año y mes en formato AAAAMM | ASRS Coding Form – TIME |
| Local Time of Day | Hora local del día en que ocurrió el evento | Categórico | 0001–0600 / 0601–1200 / 1201–1800 / 1801–2400 | ASRS Coding Form – TIME |
| AGL.Single Value | Altitud sobre el nivel del suelo (valor único) | Numérico | Valor en pies AGL | ASRS Coding Form – PLACE |
| MSL.Single Value | Altitud sobre el nivel medio del mar (valor único) | Numérico | Valor en pies MSL | ASRS Coding Form – PLACE |
| ATC Facility (ID & Type) | Identificador y tipo de instalación ATC de referencia | Texto | ID y tipo de la instalación | ASRS Coding Form – PLACE |
| Airport (ID) | Identificador del aeropuerto de referencia | Texto | Código ICAO/IATA | ASRS Coding Form – PLACE |
| NAVAID (ID & Type) | Identificador y tipo de ayuda a la navegación de referencia | Texto | ID y tipo de NAVAID | ASRS Coding Form – PLACE |
| Radial | Radial de la NAVAID de referencia | Numérico | Grados (0–360) | ASRS Coding Form – PLACE |
| Distance.Nautical Miles | Distancia a la NAVAID en millas náuticas | Numérico | Millas náuticas | ASRS Coding Form – PLACE |
| State Reference | Estado o provincia donde ocurrió el evento | Texto | Nombre del estado/provincia | ASRS Coding Form – PLACE |
| Intersection (ID) | Identificador de la intersección de referencia | Texto | ID de la intersección | ASRS Coding Form – PLACE |

- **Variable**: nombre original de la variable en el formulario ASRS.
- **Descripción**: breve descripción de la variable en español.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: sección del formulario ASRS de donde proviene la variable.

---

## Base de datos 2: Condiciones Ambientales

Condiciones meteorológicas y del entorno de trabajo al momento del evento.

| Variable | Descripción | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --- | --- | --- | --- | --- |
| Flight Conditions | Condiciones meteorológicas generales del vuelo | Categórico | VMC / IMC / Mixed / Marginal | ASRS Coding Form – ENVIRONMENT |
| Weather Elements / Visibility | Elementos meteorológicos presentes durante el evento | Categórico (múltiple) | Cloudy / Fog / Visibility (SM) / Hail / Haze/Smoke / Icing / Rain / Snow / Thunderstorm / Turbulence / Windshear / Other | ASRS Coding Form – ENVIRONMENT |
| Visibility (SM) | Visibilidad en millas estatutarias | Numérico | Valor en SM | ASRS Coding Form – ENVIRONMENT |
| RVR.Single Value | Alcance visual en pista (valor único) | Numérico | Valor en pies | ASRS Coding Form – ENVIRONMENT |
| Ceiling | Altura del techo de nubes | Categórico / Numérico | CLR / Valor en pies | ASRS Coding Form – ENVIRONMENT |
| Light | Condición de luz al momento del evento | Categórico | Dawn / Daylight / Dusk / Night | ASRS Coding Form – ENVIRONMENT |
| Work Environment Factors | Factores del entorno de trabajo que influyeron en el evento | Categórico (múltiple) | Poor Lighting / Glare / Temperature-Extreme / Excessive Humidity / Excessive Wind (UAS) | ASRS Coding Form – ENVIRONMENT |

- **Variable**: nombre original de la variable en el formulario ASRS.
- **Descripción**: breve descripción de la variable en español.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: sección del formulario ASRS de donde proviene la variable.

---

## Base de datos 3: Aeronave

Características operativas y técnicas de la(s) aeronave(s) involucrada(s).

| Variable | Descripción | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --- | --- | --- | --- | --- |
| Aircraft Operator | Tipo de operador de la aeronave | Categórico | Air Carrier / Air Taxi / Corporate / Fractional / FBO / Government / Personal / Recreational/Hobbyist (UAS) / Commercial Operator (UAS) / Other | ASRS Coding Form – AIRCRAFT |
| Aircraft Letter Reference | Letra de referencia asignada a la aeronave en el reporte | Categórico | X / Y / Z / A–W | ASRS Coding Form – AIRCRAFT |
| Flight Plan | Tipo de plan de vuelo archivado | Categórico | IFR / VFR / SVFR / DVFR / Military / None | ASRS Coding Form – AIRCRAFT |
| Operating Under FAR Part | Regulación FAR bajo la cual opera la aeronave | Categórico | Part 91 / 103 / 107 / 119 / 121 / 125 / 129 / 133 / 135 / Public Aircraft Operations (UAS) / Recreational Sec. 44809 (UAS) | ASRS Coding Form – AIRCRAFT |
| ATC/Advisory | Tipo de instalación ATC o de asesoramiento utilizado | Categórico | Center / TRACON / Tower / FSS / Ramp / CTAF / UNICOM / Military / Other | ASRS Coding Form – AIRCRAFT |
| Mission | Misión o propósito del vuelo | Categórico | Passenger / Cargo/Freight/Delivery / Training / Ferry/Re-Positioning / Ambulance / Search & Rescue / Photo Shoot/Video / Agriculture / Aerobatics / Taxi / Surveillance (UAS) / Public Safety (UAS) / Recreational (UAS) / Other | ASRS Coding Form – AIRCRAFT |
| Flight Phase | Fase del vuelo en que ocurrió el evento | Categórico | Parked / Ground/Preflight (UAS) / Takeoff/Launch / Initial Climb / Climb / Cruise / Descent / Initial Approach / Final Approach / Landing / Test Flight / Other | ASRS Coding Form – AIRCRAFT |
| Route in Use | Tipo de ruta aérea utilizada | Categórico | Airway / VFR Route / Direct / Oceanic / Vectors / STAR / SID / None / Other | ASRS Coding Form – AIRCRAFT |
| Nav in Use | Sistema de navegación utilizado durante el vuelo | Categórico | FMS/FMC / GPS / INS / Localizer/Glideslope/ILS / NDB / VOR/VORTAC | ASRS Coding Form – AIRCRAFT |
| Make Model | Marca y modelo de la aeronave | Texto | Nombre del fabricante y modelo | ASRS Coding Form – AIRCRAFT |
| Crew Size | Número de tripulantes de vuelo | Numérico | Número entero | ASRS Coding Form – AIRCRAFT |
| Airspace | Clase de espacio aéreo donde ocurrió el evento | Categórico | Class A / B / C / D / E / G / Special Use / TFR | ASRS Coding Form – AIRCRAFT |
| Maintenance Deferred? | Indica si hay mantenimiento diferido en la aeronave | Booleano | Y / N | ASRS Coding Form – AIRCRAFT |
| Records Complete? | Indica si los registros de la aeronave están completos | Booleano | Y / N | ASRS Coding Form – AIRCRAFT |
| Released for Service? | Indica si la aeronave fue liberada para servicio | Booleano | Y / N | ASRS Coding Form – AIRCRAFT |
| Required / Correct Doc on Board | Indica si la documentación requerida estaba a bordo | Booleano | Y / N | ASRS Coding Form – AIRCRAFT |
| Passengers on Board | Número de pasajeros a bordo | Numérico | Número entero | ASRS Coding Form – AIRCRAFT |
| Number of Seats | Número de asientos de la aeronave | Numérico | Número entero | ASRS Coding Form – AIRCRAFT |
| Crew Size Flight Attendant | Número de auxiliares de vuelo a bordo | Numérico | Número entero | ASRS Coding Form – AIRCRAFT |

- **Variable**: nombre original de la variable en el formulario ASRS.
- **Descripción**: breve descripción de la variable en español.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: sección del formulario ASRS de donde proviene la variable.

---

## Base de datos 4: Aeronave No Tripulada (UAS)

Variables específicas para sistemas de aeronaves no tripuladas.

| Variable | Descripción | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --- | --- | --- | --- | --- |
| Weight Category (UAS) | Categoría de peso del UAS | Categórico | Micro / Small / Medium / Large | ASRS Coding Form – AIRCRAFT (UAS) |
| Configuration (UAS) | Configuración del UAS | Categórico | Multi-Rotor / Fixed Wing / Helicopter / Hybrid / Other | ASRS Coding Form – AIRCRAFT (UAS) |
| Type (UAS) | Tipo de operación del UAS respecto a la línea de visión | Categórico | VLOS / BVLOS / Other | ASRS Coding Form – AIRCRAFT (UAS) |
| Control Mode (UAS) | Modo de control del UAS durante el evento | Categórico | Autonomous/Fully Automated / Waypoint Flying / Manual Control / Transitioning Between Modes | ASRS Coding Form – AIRCRAFT (UAS) |
| Flight Operated As (UAS) | Tipo de operación bajo la que volaba el UAS | Categórico | Standard / Special / Special Authorization Sec. 44807 | ASRS Coding Form – AIRCRAFT (UAS) |
| Flight Operated with Visual Observer (UAS) | Indica si el vuelo contó con observador visual | Booleano | Y / N | ASRS Coding Form – AIRCRAFT (UAS) |
| Number of UAS Being Controlled (UAS) | Número de UAS bajo control simultáneo del operador | Numérico | Número entero | ASRS Coding Form – AIRCRAFT (UAS) |
| Airspace Authorization Provider (UAS) | Proveedor de autorización del espacio aéreo para el UAS | Categórico | FAA Authorization / Jurisdictional COA / Emergency COA / Blanket COA / Authorized Third Party / Other | ASRS Coding Form – AIRCRAFT (UAS) |
| Waivers / Exemptions / Authorizations (UAS) | Exenciones o autorizaciones bajo las que opera el UAS | Categórico | 91 / 107.25 / 107.29 / 107.31 / 107.33 / 107.35 / 107.37(a) / 107.39 / 107.51 / 135 / Other | ASRS Coding Form – AIRCRAFT (UAS) |
| Airworthiness Certification (UAS) | Tipo de certificación de aeronavegabilidad del UAS | Categórico | Purchased Aircraft / Homebuilt/Custom / Other | ASRS Coding Form – AIRCRAFT (UAS) |
| Passenger Capable (UAS)? | Indica si el UAS es capaz de transportar pasajeros | Booleano | Y / N | ASRS Coding Form – AIRCRAFT (UAS) |
| UAS Flying In / Near / Over (UAS) | Zona o entorno donde operaba el UAS | Categórico | Airport/Aerodrome/Heliport / Critical Infrastructure / Crowds / Emergency Services / Indoor/Confined Spaces / Moving Vehicles / Natural Disaster / No Drone Zone / Open Space/Field / People/Populated Areas / Private Property / Recreational Club/Fixed Flying Site / Other | ASRS Coding Form – AIRCRAFT (UAS) |

- **Variable**: nombre original de la variable en el formulario ASRS.
- **Descripción**: breve descripción de la variable en español.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: sección del formulario ASRS de donde proviene la variable.

---

## Base de datos 5: Componente

Información sobre el componente de aeronave involucrado en el evento.

| Variable | Descripción | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --- | --- | --- | --- | --- |
| Aircraft Component | Nombre del componente de aeronave involucrado en el evento | Texto | Nombre del componente | ASRS Coding Form – COMPONENT |
| Manufacturer | Fabricante del componente involucrado | Texto | Nombre del fabricante | ASRS Coding Form – COMPONENT |
| Aircraft Reference | Letra de referencia de la aeronave a la que pertenece el componente | Categórico | X / Y / Z / Other | ASRS Coding Form – COMPONENT |
| Problem | Tipo de problema presentado por el componente | Categórico | Design / Failed / Improperly Operated / Malfunctioning | ASRS Coding Form – COMPONENT |

- **Variable**: nombre original de la variable en el formulario ASRS.
- **Descripción**: breve descripción de la variable en español.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: sección del formulario ASRS de donde proviene la variable.

---

## Base de datos 6: Persona

Información sobre las personas involucradas en el evento reportado.

| Variable | Descripción | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --- | --- | --- | --- | --- |
| Person Number | Número identificador de la persona en el reporte | Numérico | 1–30 | ASRS Coding Form – PERSON |
| Accession Number | Número de acceso del reporte ASRS | Texto | Número de acceso | ASRS Coding Form – PERSON |
| Reporter Organization | Tipo de organización de quien reporta el evento | Categórico | Air Carrier / Air Taxi / Contracted Service / Corporate / Fractional / Personal / Government / Military / FBO / Recreational/Hobbyist (UAS) / Commercial Operator (UAS) / Other | ASRS Coding Form – PERSON |
| Location of Person | Lugar físico donde se encontraba la persona al momento del evento | Categórico | Aircraft / Facility / Company / Gate/Ramp/Line / Hangar/Base / Repair Facility / Other | ASRS Coding Form – PERSON |
| Location in Aircraft | Ubicación de la persona dentro de la aeronave | Categórico | Flight Deck / Cabin Jumpseat / Crew Rest Area / Lavatory / Door Area / Galley / General Seating Area / Indoor/Ground Control Station (UAS) / Outdoor/Field Station (UAS) / Other | ASRS Coding Form – PERSON |
| Function.Flight Crew | Función de la persona en la tripulación de vuelo | Categórico | Captain / First Officer / Flight Engineer/Second Officer / Pilot Flying / Pilot Not Flying / Check Pilot / Instructor / Trainee / Relief Pilot / Single Pilot / Remote PIC (UAS) / Person Manipulating Controls (UAS) / Visual Observer (UAS) / Other/Unknown | ASRS Coding Form – PERSON |
| Qualification.Flight Crew | Habilitaciones del tripulante de vuelo | Categórico (múltiple) | Student / Private / Commercial / Air Transport Pilot (ATP) / Multiengine / Instrument / Flight Instructor / Glider / Rotorcraft / Lighter-Than-Air / Sea / Flight Engineer / Remote Pilot (UAS) / Type / Public Aircraft Operations (UAS) | ASRS Coding Form – PERSON |
| Experience.Flight Crew Total | Horas totales de vuelo del tripulante | Numérico | Horas de vuelo | ASRS Coding Form – PERSON |
| Experience.Flight Crew Last 90 Days | Horas de vuelo del tripulante en los últimos 90 días | Numérico | Horas de vuelo | ASRS Coding Form – PERSON |
| Function.Air Traffic Control | Función del controlador de tráfico aéreo | Categórico | Approach / Coordinator / Departure / Enroute / Flight Data/Clearance Delivery / Handoff/Assist / Instructor / Trainee / Supervisor/CIC / Traffic Management / Other/Unknown | ASRS Coding Form – PERSON |
| Qualification.Air Traffic Control | Calificación del controlador de tráfico aéreo | Categórico | Flight Service / Ground / Local / Oceanic | ASRS Coding Form – PERSON |
| Experience.Air Traffic Control | Experiencia del controlador por área (años) | Numérico | Años en Radar / No Radar / Military / Supervisory; Meses certificado en posición | ASRS Coding Form – PERSON |
| Function.Maintenance | Función del personal de mantenimiento | Categórico | Inspector / Instructor / Lead Technician / Parts/Stores Personnel / Quality Assurance/Audit / Trainee / Other/Unknown | ASRS Coding Form – PERSON |
| Qualification.Maintenance | Habilitaciones del personal de mantenimiento | Categórico (múltiple) | Airframe / Powerplant / Avionics / Inspector / Repairman / Nondestructive Testing / Apprentice | ASRS Coding Form – PERSON |
| Experience.Maintenance | Años de experiencia del personal de mantenimiento por área | Numérico | Años en aviónica / inspección / técnico líder / repairman / técnico | ASRS Coding Form – PERSON |
| Function.Flight Attendant | Función del auxiliar de vuelo | Categórico | Flight Attendant (On Duty) / Flight Attendant In Charge / Off Duty / Current / Other/Unknown | ASRS Coding Form – PERSON |
| FA - Cabin Activity | Actividad del auxiliar de vuelo al momento del evento | Categórico | Boarding / Deplaning / Safety Related Duties / Service | ASRS Coding Form – PERSON |
| Function.Ground Personnel | Función del personal terrestre | Categórico | Vehicle Driver / FBO Personnel / Gate Agent/CSR / Airport Personnel / Other/Unknown | ASRS Coding Form – PERSON |
| Function.Dispatch | Función del despachador | Categórico | Dispatcher | ASRS Coding Form – PERSON |
| Experience.Dispatch | Años de experiencia como despachador | Numérico | Años | ASRS Coding Form – PERSON |
| Human Factors | Factores humanos identificados en el evento | Categórico (múltiple) | Communication Breakdown / Confusion / Distraction / Fatigue / Human-Machine Interface / Physiological-Other / Situational Awareness / Time Pressure / Training/Qualification / Workload / Callback / Other/Unknown | ASRS Coding Form – PERSON |

- **Variable**: nombre original de la variable en el formulario ASRS.
- **Descripción**: breve descripción de la variable en español.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: sección del formulario ASRS de donde proviene la variable.

---

## Base de datos 7: Anomalías y Eventos

Clasificación de las anomalías, desviaciones y eventos registrados en el reporte.

| Variable | Descripción | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --- | --- | --- | --- | --- |
| Anomaly.Aircraft Equipment | Problema con equipo de la aeronave | Categórico | Critical / Less Severe | ASRS Coding Form – Events |
| Anomaly.Airspace Violation | Tipo de violación del espacio aéreo | Categórico | All Types | ASRS Coding Form – Events |
| Anomaly.ATC Issues | Problemas relacionados con ATC | Categórico | All Types | ASRS Coding Form – Events |
| Anomaly.Conflict | Tipo de conflicto aéreo o terrestre | Categórico | Airborne Conflict / Ground Conflict Critical / Ground Conflict Less Severe / NMAC | ASRS Coding Form – Events |
| Anomaly.Deviation - Altitude | Desviación de altitud asignada | Categórico | Crossing Restriction Not Met / Excursion from Assigned Altitude / All Types | ASRS Coding Form – Events |
| Anomaly.Deviation - Speed | Desviación de velocidad asignada | Categórico | All Types | ASRS Coding Form – Events |
| Anomaly.Deviation - Track/Heading | Desviación de rumbo o track asignado | Categórico | All Types | ASRS Coding Form – Events |
| Anomaly.Deviation / Discrepancy - Procedural | Desviación procedural o de documentación | Categórico | FAR / Published Material/Policy / Landing without Clearance / Maintenance / Weight and Balance / Other/Unknown | ASRS Coding Form – Events |
| Anomaly.Ground Incursion | Tipo de incursión terrestre no autorizada | Categórico | Ramp / Runway / Taxiway | ASRS Coding Form – Events |
| Anomaly.Ground Excursion | Tipo de excursión fuera del área designada en tierra | Categórico | Ramp / Runway / Taxiway | ASRS Coding Form – Events |
| Anomaly.Inflight Event/Encounter | Evento o encuentro ocurrido en vuelo | Categórico | Bird/Animal / Object / CFTT/CFIT / VFR in IMC / Fuel Issue / Laser / Wake Vortex Encounter / Weather/Turbulence / MEL/CDL / Other/Unknown | ASRS Coding Form – Events |
| Anomaly.Ground Event/Encounter | Evento o encuentro ocurrido en tierra | Categórico | Aircraft / FOD / Fuel Issue / Gear Up Landing / Ground Strike-Aircraft / Person/Animal/Bird / Ground Equipment Issue / Jet Blast / Loss of Aircraft Control / Object / Other/Unknown | ASRS Coding Form – Events |
| Anomaly.Flight Deck/Cabin/Aircraft Event | Evento ocurrido en cabina de vuelo o de pasajeros | Categórico | Illness/Injury / Passenger Electronic Device / Passenger Misconduct / Smoke/Fire/Fumes/Odor / Vehicle / Weather/Turbulence / Other/Unknown | ASRS Coding Form – Events |
| Anomaly.Other | Situación no deseada u otro tipo de anomalía no categorizada | Categórico | Unwanted Situation / Other Types | ASRS Coding Form – Events |
| Anomaly.No Specific Anomaly Occurred | Indica que no ocurrió ninguna anomalía específica | Booleano | Y / N | ASRS Coding Form – Events |
| Loss of VLOS (UAS) | Pérdida de línea de visión visual del UAS | Booleano | Y / N | ASRS Coding Form – Events |
| Fly Away (UAS) | El UAS escapó del control del operador | Booleano | Y / N | ASRS Coding Form – Events |
| Unauthorized Flight Operations (UAS) | Operación de vuelo no autorizada del UAS | Booleano | Y / N | ASRS Coding Form – Events |

- **Variable**: nombre original de la variable en el formulario ASRS.
- **Descripción**: breve descripción de la variable en español.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: sección del formulario ASRS de donde proviene la variable.

---

## Base de datos 8: Detección y Resultados

Información sobre cómo fue detectado el evento y sus consecuencias.

| Variable | Descripción | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --- | --- | --- | --- | --- |
| Detector | Quién o qué detectó el evento | Categórico | Automation (Aircraft RA / Aircraft TA / Aircraft Terrain Warning / Aircraft Other Automation) / Collision Avoidance System (UAS) / Person (Flight Crew / ATC / Maintenance / Dispatch / Gate Agent/CSR / Ground Personnel / Passenger / Observer / Other) | ASRS Coding Form – Events |
| When Detected | Momento en que fue detectado el evento | Categórico | Pre-flight / In-flight / Taxi / Aircraft in service at gate / Routine inspection / Other | ASRS Coding Form – Events |
| Were Passengers Involved in the Event? | Indica si los pasajeros estuvieron involucrados en el evento | Booleano | Yes / No | ASRS Coding Form – Events |
| Miss Distance Horizontal | Distancia horizontal de separación entre aeronaves en el evento | Numérico | Valor en pies o metros | ASRS Coding Form – Events |
| Miss Distance Vertical | Distancia vertical de separación entre aeronaves en el evento | Numérico | Valor en pies | ASRS Coding Form – Events |
| Result.General | Resultado general del evento | Categórico | Evacuated / Flight Cancelled/Delayed / Maintenance Action / Police/Security Involved / Release Refused / Overcame Equipment Problem / Work Refused / None Reported/Taken / Landed in Emergency Condition / Physical Injury/Incapacitation / Returned to Home (UAS) | ASRS Coding Form – Events |
| Result.Flight Crew | Acciones tomadas por la tripulación de vuelo ante el evento | Categórico | Became Reoriented / Diverted / Executed Go Around/Missed Approach / Inflight Shutdown / Landed as Precaution / FLC Overrode Automation / FLC Complied with Automation / Exited Penetrated Airspace / Regained Aircraft Control / Rejected Takeoff / Took Evasive Action / Returned to Departure Airport / Returned to Gate | ASRS Coding Form – Events |
| Result.Air Traffic Control | Acciones tomadas por el ATC ante el evento | Categórico | Issued New Clearance / Separated Traffic / Requested ATC Assistance/Clarification / Returned to Clearance / Provided Assistance / Issued Advisory/Alert | ASRS Coding Form – Events |
| Result.Aircraft | Estado resultante de la aeronave tras el evento | Categórico | Aircraft Damaged / Automation Overrode Flight Crew / Equipment Problem Dissipated / Automated Return to Home (UAS) / Lost/Unrecoverable (UAS) / Lost Link (UAS) | ASRS Coding Form – Events |

- **Variable**: nombre original de la variable en el formulario ASRS.
- **Descripción**: breve descripción de la variable en español.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: sección del formulario ASRS de donde proviene la variable.

---

## Base de datos 9: Factores Contribuyentes y Problema Principal

Evaluación de los factores que contribuyeron al evento y el problema principal identificado.

| Variable | Descripción | Tipo de dato | Rango/Valores posibles | Fuente de datos |
| --- | --- | --- | --- | --- |
| Contributing Factors / Situations | Factores y situaciones que contribuyeron al evento | Categórico (múltiple) | Aircraft / Airport / Airspace Structure / ATC Equip/Nav Facility/Buildings / Chart or Publication / Company Policy / Equipment/Tooling / Environment-Non Weather Related / Human Factors / Manuals / MEL / Procedure / Staffing / Weather / Software and Automation / Incorrect/Not Installed/Unavailable Part / Logbook Entry | ASRS Coding Form – Assessments |
| Primary Problem | Problema principal identificado como causa raíz del evento | Categórico | Aircraft / Airport / Airspace Structure / Company Policy / Equipment/Tooling / Chart or Publication / Weather / Ambiguous / Logbook Entry / Manuals / Software and Automation / Procedure / Staffing / MEL | ASRS Coding Form – Assessments |

- **Variable**: nombre original de la variable en el formulario ASRS.
- **Descripción**: breve descripción de la variable en español.
- **Tipo de dato**: tipo de dato que contiene la variable.
- **Rango/Valores posibles**: rango o valores que puede tomar la variable.
- **Fuente de datos**: sección del formulario ASRS de donde proviene la variable.

---

## Glosario de siglas

| Sigla | Significado |
| --- | --- |
| AGL | Above Ground Level (Sobre el nivel del suelo) |
| ATC | Air Traffic Control (Control de tráfico aéreo) |
| ATP | Air Transport Pilot (Piloto de transporte aéreo) |
| BVLOS | Beyond Visual Line of Sight (Más allá de la línea de visión visual) |
| CFTT/CFIT | Controlled Flight into Terrain (Vuelo controlado hacia el terreno) |
| COA | Certificate of Authorization (Certificado de autorización) |
| CTAF | Common Traffic Advisory Frequency (Frecuencia común de aviso de tráfico) |
| FBO | Fixed Base Operator (Operador de base fija) |
| FMS/FMC | Flight Management System/Computer (Sistema/computador de gestión de vuelo) |
| FOD | Foreign Object Debris (Objeto extraño en área de operaciones) |
| FSS | Flight Service Station (Estación de servicio de vuelo) |
| IMC | Instrument Meteorological Conditions (Condiciones meteorológicas por instrumentos) |
| MEL | Minimum Equipment List (Lista de equipo mínimo) |
| MSL | Mean Sea Level (Nivel medio del mar) |
| NDT | Nondestructive Testing (Pruebas no destructivas) |
| NMAC | Near Midair Collision (Casi colisión en vuelo) |
| PIC | Pilot in Command (Piloto al mando) |
| RVR | Runway Visual Range (Alcance visual en pista) |
| SID | Standard Instrument Departure (Salida instrumental estándar) |
| STAR | Standard Terminal Arrival Route (Ruta estándar de llegada terminal) |
| UAS | Unmanned Aircraft System (Sistema de aeronave no tripulada) |
| VMC | Visual Meteorological Conditions (Condiciones meteorológicas visuales) |
| VLOS | Visual Line of Sight (Línea de visión visual) |
