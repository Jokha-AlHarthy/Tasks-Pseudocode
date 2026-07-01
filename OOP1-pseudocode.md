Task 279: Movie Theater

Blueprint:

CLASS FILM
	ATTRIBUTES
		id: NUMBER
		title: TEXT
		duration: NUMBER
		caption: TEXT
		filmType: TEXT
		showtimes: LIST OF SHOWTIMES

	
	CONTRACTOR (title: TEXT, duration: NUMBER, caption: TEXT,filmType: TEXT)
		SET THIS.title TO title
		SET THIS.duartion TO duration
		SET THIS.caption TO caption
		SET THIS.filmType TO filmType
	END CONSTRCTOR

	METHODS
		ADDSHOWRIME(show: SHOWTIMES)
			ADD show TO showtimes
		END METHOD
	
		GET_id()
			DISPLAY id
		END METHOD

		GET_title()
			DISPLAY title
		END METHOD

		GET_duration()
			DISPLAY duration
		END METHOD

		SET_duration(newDuration: TEXT)
			IF LENGTH OF newDuration GREATHER THAN 0 THEN
				SET duration TO newDuration
			ELSE
				DISPLAY "Error assigning time duration"
			END IF
		END METHOD

		GET_caption()
			DISPLAY caption
		END METHOD

		GET_filmType()
			DISPLAY filmtype
		END METHOD

END CLASS


CLASS SHOWTIME
	ATTRIBUTES
		id: NUMBER
        	date: TEXT
        	time: TEXT
        	screen: SCREEN
        	tickets: LIST OF TICKET
	CONSTRUCTOR(date: TEXT, time: TEXT, screen: SCREEN)
        	SET THIS.date TO date
        	SET THIS.time TO time
        	SET THIS.screen TO screen
    	END CONSTRUCTOR

	METHODS
	
		ADDTICKET(ticket: TICKET)
			ADD ticket TO tickets
		END METHOD
 
		GET_id()
			DISPLAY id
		END METHOD
	
		GET_date()
			DISPLAY date
		END METHOD

		SET_date(newDate: TEXT)
			DISPLAY "Enter date you want for the show"
			SET date TO newDate
		END METHOD()


		GET_time()
			DISPLAY time
		END METHOD

		SET_time(newTime: TEXT)
			DISPLAY "Enter time you want for the show"
			SET time TO newTime
		END METHOD()

		GET_screen()
			DISPLAY screen
		END METHOD

		DISPLAYSHOWTIME()
            		DISPLAY id
            		DISPLAY date
            		DISPLAY time
        	END METHOD

END CLASS

CLASS SCREEN
	ATTRIBUTES
		id: NUMBER
        	screenName: TEXT
		capcity: NUMBER

	CONSTRUCTOR(screenName: TEXT, capacity: NUMBER)
        	SET THIS.screenName TO screenName
        	SET THIS.capacity TO capacity
    	END CONSTRUCTOR
	
	METHODS
		GET_id()
			DISPLAY id
		END METHOD

		GET_screenName()
			DISPLAY screenName
		END METHOD
		GET_capcity()
			DISPLAY capcity
		END METHOD
	
 		DISPLAYSCREEN()
            		DISPLAY id
            		DISPLAY screenName
            		DISPLAY capacity
        	END METHOD
	
END CLASS

CLASS TICKET
	ATTRIBUTES
		id: NUMBER
        	custName: TEXT
		seatNumber: NUMBER

	CONSTRUCTOR(custName: TEXT, seatNumber: NUMBER)
        	SET THIS.custName TO custName
        	SET THIS.seatNumber TO seatNumber
    	END CONSTRUCTOR

	METHODS
		GET_id()
			DISPLAY id
		END METHOD

		GET_custName()
           		 DISPLAY custName
        	END METHOD

      		GET_seatNumber()
            		DISPLAY seatNumber
        	END METHOD

		SET_custName(newCust: TEXT)
			DISPLAY "PLease enter your name:"
			SET custName TO newCust
		END METHOD

		seatNumber(newSeat: NUMBER)
			DISPLAY "Please enter seat number"
			IF newSEAT GREATER THAN 0 THEN
				DISPLAY "Seat booked Successfully"
			ELSE
				DISPLAY "Error, no seat with this number please start from 1"
		END METHOD
		PRINTTICKET()
			DISPLAY id
			DISPLAY custName
			DISPLAY seatNumber
		END METHOD


END CLASS

pseudocode:

START
	BEGIN
		CREATE OBJECT film1 OF FILM (1, "Avater", 180, "Action")
		CREATE OBJECT screen1 OF SCREEN(1, "screen A", 150)
		CREATE OBJECT show1 OF SHOWTIME(101, "02-July-2026", "7:00 PM", screen1)
		CREATE OBJECT ticket1 OF TICKER(5001, "Ahmed ali", 25)

		film1.ADDSHOWTIME(show1)
		show1.ADDTIRCKT(ticket1)

	
		show1.DISPLAYSHOWTIME()
        	screen1.DISPLAYSCREEN()
        	ticket1.PRINTTICKET()
	END
STOP
