# Artifact III
## Enhancement: Databases

### Description & Justification

This artifact was originally created for my CS340 course client/server development back in summer of 2020. It is a combination of Python code that implements CRUD operations on a database which was originally implemented through MongoDB, and a Jupyter Notebook code that displayed the database data visual through a web browser-based GUI. 

I chose to include this artifact set in the ePortfolio as it highlights skills in both web browser layout/design and database access/control. It combines the utilization of Python language to provide functions that control the database and HTML for the display of data in within a browser, thereby showcasing two separate language skill sets. The artifact was enhanced through the addition of username and password validation to enhance security.
```markdown
 # Username and password once validated, are fed to AnimalShelter class Python module
 username = "aacuser2"
 password = "password"

 while True: 
     a = str(input("Enter username:"))
     if (len(a) >= 15) or a != username:
         print("Username invalid")
     elif a == username:
         break

 while True:
     b = str(input("Enter password:"))
     if (len(b) != 8) or b != password:
         print("Password invalid")
     elif b == password:
         break

 username = a
 password = b
            
 shelter = AnimalShelter(username, password)
```
This demonstrates achievement of the course outcome of developing a security mindset as user input exploitations are quite common. The username and password input are validated by length and equivalency to avoid these exploits of a user inputting extra information to cause buffer overflow for example. The functionality of the code was also improved by the addition of radio buttons to the Jupyter Notebook user interface for proper filtration of database data. 
```markdown
 # Creates container for radio button filters to filter and reset table results
    html.Div(
        dcc.RadioItems(
            id='filters',
            # Creats labels and values for radio button filters
            options=[
            {'label': 'Water Rescue', 'value': '0'},
            {'label': 'Mountain/Wilderness Rescue', 'value': '1'},
            {'label': 'Disaster Rescue/Individual Tracking', 'value': '2'},
            {'label': 'Reset - returns unfiltered state', 'value': '3'}
            ],
            value='RESET',
            labelStyle={'display': 'inline-block'}
        )
    ),
```
The pie chart feature was also fixed to improve user experience by providing relevant data visually. 
```markdown
 # Updates Pie Chart based on row selection
 @app.callback(
     Output('graph-id', "children"),
     [Input('datatable-interactivity', "derived_viewport_data")]
 )
 def update_graphs(viewData):
     dff = pd.DataFrame.from_dict(viewData)
    
     names = dff['breed'].value_counts().keys().tolist()
     values = dff['breed'].value_counts().tolist()
    
     return [
         dcc.Graph(id='pie-chart',            
             figure = px.pie(
                 data_frame=dff, 
                 values = values, 
                 names = names,
                 color_discrete_sequence = px.colors.sequential.RdBu,
                 width = 700,
                 height = 400, 
             )
         )
     ]
```
The map feature as well was expanded to allow for multiple user selections to be displayed and viewed on the map. 

```markdown
 if len(selected_rows) == 3:
        return [
            dl.Map(style={'width':'1000px', 'height': '500px'}, center=[30.75,-97.48], zoom=10, children=[
                dl.TileLayer(id="base-layer-id"),
            
                #marker with tool tip and popup
                dl.Marker(position=[(dff.iloc[selected_rows[0],13]), (dff.iloc[selected_rows[0],14])], children=[
                    dl.Tooltip(dff.iloc[selected_rows[0],4]),
                    dl.Popup([
                        html.H4("Animal Name"),
                        html.P(dff.iloc[selected_rows[0],9]),
                        html.H4("Sex"),
                        html.P(dff.iloc[selected_rows[0],12]),
                        html.H4("Breed"),
                        html.P(dff.iloc[selected_rows[0],4]),
                        html.H4("Age"),
                        html.P(dff.iloc[selected_rows[0],15])
                    ])
                ]),
                dl.Marker(position=[(dff.iloc[selected_rows[1],13]), (dff.iloc[selected_rows[1],14])], children=[
                    dl.Tooltip(dff.iloc[selected_rows[1],4]),
                    dl.Popup([
                        html.H4("Animal Name"),
                        html.P(dff.iloc[selected_rows[1],9]),
                        html.H4("Sex"),
                        html.P(dff.iloc[selected_rows[1],12]),
                        html.H4("Breed"),
                        html.P(dff.iloc[selected_rows[1],4]),
                        html.H4("Age"),
                        html.P(dff.iloc[selected_rows[1],15])
                    ])
                ]),
                d1.Marker(position=[(dff.iloc[selected_rows[2],13]), (dff.iloc[selected_rows[2],14])], children=[
                    d1.Tooltip(dff.iloc[selected_rows[2],4]),
                    d1.Popup([
                        html.H4("Animal Name"),
                        html.P(dff.iloc[selected_rows[2],9]),
                        html.H4("Sex"),
                        html.P(dff.iloc[selected_rows[2],12]),
                        html.H4("Breed"),
                        html.P(dff.iloc[selected_rows[2],4]),
                        html.H4("Age"),
                        html.P(dff.iloc[selected_rows[2],15])
                    ])
                ])
            ])
        ]
```
These visual additions demonstrate achieving the course outcome of delivering professional-quality visual communications as these features are specifically tailored to the specific user utilizing this artifact for database use.

### Reflection

Overall, through my enhancement and modification of this artifact I learned the most. This project, when completed for my previous course, was very environment driven. To perform my enhancements, I had to setup Jupyter Lab on my own computer, as I didn’t have access to the virtual desktop I was utilizing for the course previously. This meant manually setting up the proper environment through my computers command line. Installing the proper libraries, I needed to import into the project. This was a challenge as I had to go back a few times to find the proper libraries to utilize as there were some inconsistencies. It was great to learn the process of setting up Jupyter Notebook on the backend as this was previously taken care of for us during the course, and once this was done the improvements went fairly smoothly. 

**Repository Link**<br>

[Original Artifact III](https://github.com/Shayden87/CS340) <br>
[Enhanced Artifact III](https://github.com/Shayden87/Databases)

**ePortfolio Links** <br> 

* [Artifact I](ArtifactOne.md)
* [Artifact II](ArtifactTwo.md)
* [Code Review](CodeReview.md)
* [Home](index.md)
