# BingoSurvey
## A new unique way to conduct surveys or even create games!

### What is BingoSurvey? 
Bingo Survey is a webapp that allows for the formatting of a survey as a bingo board. This allows for a more interactive and fun way to conduct surveys. Administrators can create boards, and users can fill them out. The results are then stored in a database and can be exported to a CSV file.

### Features
- Surveys as bingo boards!
- Results can be exported to a CSV file.
- Active and inactive boards—only active boards can be played.
  - Multiple boards can be active at once.
- User accounts—you must be registered to play.

### How to run BingoSurvey (in development mode)
1. Clone the repository.

2. Create a virtual environment using venv:
```bash
python -m venv venv
```

3. Install the required packages using pip:
```bash
pip install -r requirements.txt
```

4. Create a ``.env`` file in the root directory with the following contents:
```
SECRET_KEY="<your_secret_key>"
DATABASE_URI="mysql://username:password@address:port/database"
SESSION_COOKIE_SECURE=<True/False>
SESSION_COOKIE_HTTPONLY=<True/False>
SESSION_COOKIE_SAMESITE="<Strict/Lax/None>"
```
``SECRET_KEY`` is used to encrypt the session cookies. To generate one, consider using the ``secrets`` module in Python. For example:
```python
import secrets
secret_key = secrets.token_hex(25)
print(secret_key)
```
You can change the length of the secret key by changing the number in ``secrets.token_hex()``. Replace ``your_secret_key`` with the generated secret key.

``DATABASE_URI`` is the URI to your database. The general format is ``mysql://username:password@address:port/database``. Replace ``username``, ``password``, ``address``, ``port``, and ``database`` with your database's information. If your database software is different, you can change the URI to match your database's URI. Keep in mind that this app was developed using SQLAlchemy, so the URI should be compatible with SQLAlchemy.

``SESSION_COOKIE_SECURE`` determines if the session cookie is secure. If you are using HTTPS, set this to ``True``. If you are using HTTP, set this to ``False``.

``SESSION_COOKIE_HTTPONLY`` determines if the session cookie is HTTP only. If you want to prevent JavaScript from accessing the session cookie, set this to ``True``. If you want JavaScript to access the session cookie, set this to ``False``.

``SESSION_COOKIE_SAMESITE`` determines the SameSite attribute of the session cookie. If you want to prevent the session cookie from being sent in a cross-site request, set this to ``"Strict"``. If you want the session cookie to be sent in a cross-site request, set this to ``"Lax"``. If you want the session cookie to be sent in a cross-site request and you want to prevent the session cookie from being sent in a cross-site request from a different site, set this to ``"None"``.

5. Run the app using either ``start_dev.sh`` or ``start_dev.bat``:

For Linux and macOS:
```bash
./start_dev.sh
```

For Windows:
```powershell
start_dev.bat
```

### How to deploy BingoSurvey (in production mode)
*This section is a work in progress. Please check back later for a more finalized version. Thanks!*


### How to use BingoSurvey
#### Administration
Everything for administration is done through the command line (for now).
The administration script is located at ``admin/admin.py``. To run the script, use the following command:
```bash
python admin/admin.py
```

You will be greeted with a menu. The CLI is (in my opinion) very intuitive—and dare I say, friendly—but everything you need to know is located in the GitHub Wiki for this project.

### What is the story behind BingoSurvey?
BingoSurvey originated from a request from a friend I know from Lafayette College. He asked me if I knew of any websites that allowed for a progressive game to be played with a bingo board style survey component. He was planning a game about networking and wanted to have a week-long game where people could fill out a survey in the form of a bingo board. Since I couldn't find any websites that did this (and I was on spring break), I decided to make one myself.

### What is the future of BingoSurvey?
Here's a short (hopefully up-to-date) list of features that I'd love to implement in the future:
- [ ] Question Types
  - Currently, the only question type is a text input. It would be nice to have multiple question types, such as multiple choice, checkboxes, etc.
- [ ] More robust export functionality
  - Currently, the export functionality is very basic. It would be nice to have a more robust export functionality, such as the ability to export only certain columns, or to export only certain rows, or even to export multiple surveys into one file. Also, the ability to export to other file types, such as plaintext or Excel excites me.
- [ ] More robust user accounts
  - Currently, the only thing you can do with a user account is to play a board. It would be nice to have more robust user accounts, such as the ability to create boards, or to view past results.
You can see the full list of features I'd like to implement in the TODO.md file.

### Reporting a bug
If you find a bug, please create an issue on GitHub and add the "bug" label. Please include as much information as possible, such as the steps to reproduce the bug, the expected behavior, and the actual behavior.

### How to contribute
If you have any ideas for features, please let me know by creating an issue on GitHub and adding the "suggestion" label. Or, if you're feeling ambitious, you can fork the repository and create a pull request with your feature implemented! There are no requirements for contributing, apart from ensuring that your code is documented.

### Contact
If you have any questions, please feel free to reach out to me:
- GitHub Issue Tracker (preferred for bug reports and feature suggestions or other things related to the project)
- Email (better for other inquiries): [eshbaugj@lafayette.edu](mailto:eshbaugj@lafayette.edu)

### License

    Copyright (C) 2024 Jackson Eshbaugh
    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, version 3 of the License.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License (LICENSE) for more details.