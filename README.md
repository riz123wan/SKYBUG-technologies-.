# SKYBUG-technologies-.
 Simple Calculator In Python programming.
 contacts = {}

def add_contact(name, phone, email, address):
    contacts[name] = {'Phone': phone, 'Email': email, 'Address': address}
    print(f'Contact "{name}" added successfully!')
def view_contact_list():
    if contacts:
        print("Contact List:")
        for name, details in contacts.items():
            print(f"{name}: {details['Phone']}")
    else:
        print("No contacts found.")
def search_contact(search_term):
    results = [name for name in contacts if search_term.lower() in name.lower() or search_term in contacts[name]['Phone']]
    if results:
        print("Search Results:")
        for name in results:
            print(f"{name}: {contacts[name]['Phone']}")
    else:
        print("No matching contacts found.")
def update_contact(name, phone, email, address):
    if name in contacts:
        contacts[name] = {'Phone': phone, 'Email': email, 'Address': address}
        print(f'Contact "{name}" updated successfully!')
    else:
        print(f'Contact "{name}" not found.')
def delete_contact(name):
    if name in contacts:
        del contacts[name]
        print(f'Contact "{name}" deleted successfully!')
    else:
        print(f'Contact "{name}" not found.')
while True:
    print("\n1. Add Contact\n2. View Contact List\n3. Search Contact\n4. Update Contact\n5. Delete Contact\n6. Exit")
    choice = input("Enter your choice (1-6): ")
    if choice == '1':
        name = input("Enter name: ")
        phone = input("Enter phone number: ")
        email = input("Enter email: ")
        address = input("Enter address: ")
        add_contact(name, phone, email, address)
    elif choice == '2':
        view_contact_list()
    elif choice == '3':
        search_term = input("Enter name or phone number to search: ")
        search_contact(search_term)
    elif choice == '4':
        name = input("Enter name to update: ")
        phone = input("Enter new phone number: ")
        email = input("Enter new email: ")
        address = input("Enter new address: ")
        update_contact(name, phone, email, address)
    elif choice == '5':
        name = input("Enter name to delete: ")
        delete_contact(name)
    elif choice == '6':
        break
    else:
        print("Invalid choice. Please enter a number between 1 and 6.")
    
