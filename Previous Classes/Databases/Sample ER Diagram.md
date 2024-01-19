![[Drawing 2023-09-05 17.37.47.excalidraw]]
Audience
- Age - Int
- Region - Int
- TicketID
	- Date - Date
	- Time - Time
- Primary Key: TicketID
DVD
- Blu-Ray - Bool
- Primary Key: Barcode (Parent: Media)
Media
- Barcode - Int
- Price - Float
- Region - Integer
- Primary Key: Barcode
Movies
- Director - Varchar(80)
- Duration - Int
- Genre - Varchar(80)
- MovID - Int
- Title - Varchar(80)
- Primary Key: MovID
Pirate
- Application - Varchar(80)
- GuildKey - Int
- Handle - Varchar(80)
- Quality - Varchar(16)
- Seeders - Int
- Virus - Bool
- Primary Key: GuildKey
Score
- Count - Int
- Rating - 
- Service - Var(80)
- ServiceKey - Int
- Year - Year
- Surrogate Key: ServiceKey
Streaming
- ServiceName - Varchar(80)
- Primary Key: Parent Media: barcode
Studio
- Address - Varchar(80)
- Name - Varchar(80)
- TaxID - Int
- Primary Key: TaxID
Theater
- Name - Varchar(80)
- Screen# - Int
- ScreenType - Multivariate
- TaxID - INt
- Primary Key: TaxID
Theater Disc
- Format - Varchar(80)
- Primary Key: Barcode (from Media)
Writer
- \#Oscars - Int
- GuildID - Int
- Name - Varchar(80)
- primary key: GuildID


Produces
* Entities: Movie, Studio
* Participants: Total, Partial
* Cardinality: Many to Many