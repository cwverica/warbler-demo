>items marked with a "++" have been addressed

>items marked with a "+" are in process of being addressed

---

### In models.py:

    Bug:   ++
        For models 'Likes' (line 30), 'User' (line 52), 'Message' (line 173):
            'id' column is primary key, never utilized/required during signup
    Fix:
        add parameter 'autoincrement=True'

    Bug:   ++
        In classmethod 'signup' (line 134):
            On line 149, user added to session, never committed. 
    Fix:
        Commit (db.session.commit())

    Bug (potential):
        For model 'Likes; (line 30):
            message_id column set to 'unique=True' (line 48)
            may prevent more than one user from liking a message? verify
    Fix (potential):
        Set unique parameter to False (or remove, because unique defaults to False)

    Bug (or just sloppy code):  +
        Relationship between User and Message:
            Poorly defined, also slightly redundant
    Fix:
        Verify that no more parameters are needed, if they are fix
        At the least, set 'backref="user"' on line 97 delete statement on line 200

    Bug/Consistency Error:  ++
        On lines [19, 25, 42, 47] 'ondelete=cascade' is lowercase, on line 196 'CASCADE'
        is uppercased. If it's not a bug it's inconsistent
    Fix:
        change 'CASCADE' to 'cascade' (at the very least for consistency)
    

### In app.py:

    Implement:  ++
        logout route/function (line 116)

    Implement:  ++
        edit profile route/function (line 214)

    Bug:  ++
        In app route 'messages_destroy' (line 268):
            validates a user is logged in. does not validate that user is author of message
    Fix:
        Add additional validation to check that user logged in is author,
        otherwise, flash permission error, redirect


### In detail.html:

    Implement:  ++
        Likes stats/link (line 32)

    Implement:  ++
        Bio information (line 61)

    Implement:  ++
        Location information (line 62)

### In followers.html:

    Implement:
        Add alt for image (line 13) if relevant

    Implement:  ++
        Bio information/link (line 33)

### In following.html:

    Implement:
        Add alt for image (line 12) if relevant

    Implement:  ++
        Bio information/link (line 31) if relevant

### In index.html:

    Implement:
        Add alt for image (line 16) if relevant

    Implement:  ++
        Bio information/link (line 39)

### In show.html:

    Bug (potential):
        Self closing link tag (line 9)
    Fix (potential):
        Not really sure there's a problem, just not sure what the intention
        is there. Verify on first run.

### In home.html:

    Implement:
        Add alt for image (line 9) if relevant

