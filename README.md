# contactbook
def add_contact(contact_book, name, phone_number):
    """Adds a contact to the contact book."""
    if name in contact_book:
        print(f"Contact with name {name} already exists.")
    else:
        contact_book[name] = phone_number
        print(f"Contact {name} added successfully.")

def find_contact(contact_book, name):
    """Finds a contact in the contact book."""
    if name in contact_book:
        phone_number = contact_book[name]
        print(f"Contact {name}: {phone_number}")
    else:
        print(f"Contact {name} not found.")

def delete_contact(contact_book, name):
    """Deletes a contact from the contact book."""
    if name in contact_book:
        del contact_book[name]
        print(f"Contact {name} deleted successfully.")
    else:
        print(f"Contact {name} not found.")

def list_contacts(contact_book):
    """Lists all contacts in the contact book."""
    if len(contact_book) > 0:
        for name, phone_number in contact_book.items():
            print(f"Contact: {name}, Phone Number: {phone_number}")
    else:
        print("No contacts found.")

def main():
    contact_book = {}

    while True:
        print("\nMain Menu:")
        print("1. Add Contact")
        print("2. Find Contact")
        print("3. Delete Contact")
        print("4. List Contacts")
        print("5. Exit")

        choice = int(input("Enter your choice: "))

        if choice == 1:
            name = input("Enter contact name: ")
            phone_number = input("Enter contact phone number: ")
            add_contact(contact_book, name, phone_number)
        elif choice == 2:
            name = input("Enter contact name to find: ")
            find_contact(contact_book, name)
        elif choice == 3:
            name = input("Enter contact name to delete: ")
            delete_contact(contact_book, name)
        elif choice == 4:
            list_contacts(contact_book)
        elif choice == 5:
            print("Exiting contact book application.")
            break
        else:
            print("Invalid choice. Please enter a valid option (1-5).")

if __name__ == "__main__":
    main()
