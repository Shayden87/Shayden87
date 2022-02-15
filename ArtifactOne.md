# Artifact I
## Enhancement: Software Design/Engineering

### Description & Justification
This artifact is an implementation of a constructor and list/array through the Python language. It creates appointment objects through the Appointment class then allows them to be added to list/array through the AppointmentService class. The AppointmentService class also allows for the update and removal of objects from the list/array. It was originally created in Java back in 2020 and translated to Python in January 2022.

I included this artifact in my ePortfolio as it highlights my skills in the software design/engineering process. As the artifact also includes a Python unit test protocol it provides demonstration of skills that span the entire software development lifecycle from development of code to testing of that code. 
```markdown
class Test(unittest.TestCase):

    #Test to verify adding of appointment to list
    def testAddAppointment(self):
        a = Appointment('00001', date(2022, 12, 1), 'Coffee with Brian')
        b = Appointment('00002', date(2022, 12, 3), 'Meeting with Allison')
        c = Appointment('00003', date(2022, 12, 4), 'Conference in Chicago')
        self.assertEquals(True, AppointmentService.add_appointment(a))
        self.assertEquals(True, AppointmentService.add_appointment(b)) 
        self.assertEquals(True, AppointmentService.add_appointment(c)) 
    
    #Test to verify long id length throws Value Error
    def testIdLong(self):
        with self.assertRaisesRegexp(ValueError, 'Invalid id'): 
            a = Appointment('55502100000', date(2022, 12, 1), 'Business Meeting with share holders')
            AppointmentService.add_appointment(a)
```
The artifact showcases my skills in the use of data structures and creation of modular code that is clean, maintainable, and easy to understand. The artifact itself was improved through removing of redundant code and unnecessary methods, clean up of structural irregularity, addition of clear comments within code, and the translation from Java to Python. This translation of code from one language to another also demonstrates skills and strengths in software design/engineering by implementing code solutions through multiple languages.
```markdown
**_Java Example_**

//constructor//
		public Appointment(String id, LocalDate date, String description) {
			if(id == null || id.length() > 10) {
				throw new IllegalArgumentException("Invalid input");
			}
			if(date == null || date.isBefore(LocalDate.now())) {
				throw new IllegalArgumentException("Invalid date");
			}
			if(description == null || description.length() > 50) {
				throw new IllegalArgumentException("Invalid input");
			}
			this.id = id;
			this.date = date;
			this.description = description;
		}
```
```markdown
**_Python Example_**

#Constructor
    def __init__(self, appt_id, date, description):
        if(appt_id == None or len(appt_id) >= 10):
            raise ValueError('Invalid id')
        if(date == None or date < (date.today())):
            raise ValueError('Invalid date')
        if(description == None or len(description) > 50):
            raise ValueError('Invalid description')
        
        self.appt_id = appt_id
        self.date = date
        self.description = description
```
The above code snippet also demonstrates an example of developing a security mindset by mitigating of potential vulnerabilities in code through both input validation and error 
handling. 

### Reflection

Through my refinement of this artifact, I learned quite a bit about my own work. I realized that my previous work in creation of the original artifact may have been in haste. While being able to code quickly can be an asset it should never come at the cost of quality of the work. There must be a balance struck between the two, especially in context of the professional realm and working for a client. Being able to go back I was able to find code that was redundant or unnecessary. Leaving this code would be a detriment to the artifact and present potential issues down the line if code were to be reused or modified. The challenges I faced during my enhancements lied within the translation of code from Java to Python. While I find Python more straightforward, there are some capabilities within Java that make creation of data structures more detailed. Finding equivalent code capabilities within Python was challenging, but in the end, I felt the code was easier to read. 

**Repository Link**<br>

[Original Artifact I](https://github.com/Shayden87/CS320) <br>
[Enhanced Artifact I](https://github.com/Shayden87/Software-Engineering-Design)

**ePortfolio Links** <br> 

* [Artifact II](ArtifactTwo.md)
* [Artifact III](ArtifactThree.md)
* [Code Review](CodeReview.md)
* [Home](index.md)
