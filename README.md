
# Simplest GST Billing app.

* Easily create invoices
* Manage inventory
* Keep books and track balances



virtualenv -p python3 venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver

