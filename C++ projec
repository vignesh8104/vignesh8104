#include <iostream>
#include <iomanip>
#include <cstdlib>  // for rand() function
#include <algorithm>  // for std::transform

class Student {
private:
    std::string firstName;
    std::string surName;
    std::string studentEmail;
    std::string fatherName;
    std::string motherName;
    long long phoneNumber;
    float tenthGradeMarks;
    float twelfthGradeMarks;
    std::string branch;
    std::string rollNumber;
    std::string residenceType; // "Bus" or "Hostel"
    std::string residentialArea;
    std::string state;
    std::string roomSharingPreference;

public:
    // Constructor to initialize default values
    Student() : phoneNumber(0), tenthGradeMarks(0.0), twelfthGradeMarks(0.0) {}

    // Member functions to set and get values
    void setStudentDetails();
    bool checkEligibility() const;
    void chooseBranch();
    void chooseResidenceType();
    void provideResidenceDetails();
    void generateRollNumberAndEmail();
    void displayInformation() const;
    void calculateFee() const;
};

void Student::setStudentDetails() {
    std::cout << "Enter Student First Name: ";
    std::getline(std::cin, firstName);

    std::cout << "Enter Student Surname: ";
    std::getline(std::cin, surName);

    std::cout << "Enter Father's Name: ";
    std::getline(std::cin, fatherName);

    std::cout << "Enter Mother's Name: ";
    std::getline(std::cin, motherName);

    std::cout << "Enter Phone Number: ";
    std::cin >> phoneNumber;

    std::cout << "Enter 10th Grade Marks: ";
    std::cin >> tenthGradeMarks;

    std::cout << "Enter 12th Grade Marks: ";
    std::cin >> twelfthGradeMarks;

    std::cout << "\nThanks for filling your details. Please wait..." << std::endl;
    std::cout << "---------------------------------------------" << std::endl;
    std::cout << "After verifying your information." << std::endl;
}

bool Student::checkEligibility() const {
    return (tenthGradeMarks >= 60.0 && twelfthGradeMarks >= 60.0);
}

void Student::chooseBranch() {
    std::cout << "\nCongratulations! You are eligible to choose a branch.\n";
    std::cout << "Believe you can and you're halfway there. -" << std::endl;
    std::cout << "---------------------------------------------" << std::endl;
    std::cout << "Choose your branch:\n";
    std::cout << "1. Computer Science\n";
    std::cout << "2. Electrical Engineering\n";
    std::cout << "3. Mechanical Engineering\n";
    std::cout << "4. Civil Engineering\n";
    std::cout << "Enter your choice (1-4): ";

    int choice;
    std::cin >> choice;

    switch (choice) {
        case 1:
            branch = "Computer Science";
            break;
        case 2:
            branch = "Electrical Engineering";
            break;
        case 3:
            branch = "Mechanical Engineering";
            break;
        case 4:
            branch = "Civil Engineering";
            break;
        default:
            std::cout << "Invalid choice. Exiting.\n";
            exit(0);
    }
}

void Student::chooseResidenceType() {
    std::cout << "\nChoose your residence type:\n";
    std::cout << "1. Bus\n";
    std::cout << "2. Hostel\n";
    std::cout << "Enter your choice (1 or 2): ";

    int choice;
    std::cin >> choice;

    switch (choice) {
        case 1:
            residenceType = "Bus";
            break;
        case 2:
            residenceType = "Hostel";
            break;
        default:
            std::cout << "Invalid choice. Exiting.\n";
            exit(0);
    }
}

void Student::provideResidenceDetails() {
    std::cout << "\nEnter your residential area: ";
    std::cin.ignore();  // Clear the newline character from the buffer
    std::getline(std::cin, residentialArea);

    std::cout << "Enter the state you belong to: ";
    std::getline(std::cin, state);

    if (residenceType == "Hostel") {
        std::cout << "Choose room sharing preference:\n";
        std::cout << "1. 2 Sharing\n";
        std::cout << "2. 4 Sharing\n";
        std::cout << "3. 6 Sharing\n";
        std::cout << "Enter your choice (1-3): ";

        int sharingChoice;
        std::cin >> sharingChoice;

        switch (sharingChoice) {
            case 1:
                roomSharingPreference = "2 Sharing";
                break;
            case 2:
                roomSharingPreference = "4 Sharing";
                break;
            case 3:
                roomSharingPreference = "6 Sharing";
                break;
            default:
                std::cout << "Invalid choice. Exiting.\n";
                exit(0);
        }
    }
}

void Student::generateRollNumberAndEmail() {
    // Transform names to lowercase for email
    std::transform(firstName.begin(), firstName.end(), firstName.begin(), ::tolower);
    std::transform(surName.begin(), surName.end(), surName.begin(), ::tolower);

    // Create email ID
    studentEmail = firstName + "_" + surName + "@srmap.edu.in";

    // Generate roll number
    rollNumber = "AP221100101" + std::to_string(rand() % 1000 + 1);  // Random roll number
}

void Student::displayInformation() const {
    std::cout << "\nCongratulations! You have successfully registered.\n";
    std::cout << "---------------------------------------------" << std::endl;
    std::cout << "Roll Number: " << rollNumber << std::endl;
    std::cout << "Email ID: " << studentEmail << std::endl;
    std::cout << "Branch: " << branch << std::endl;

    if (residenceType == "Bus") {
        std::cout << "Residence Type: Bus\n";
    } else {
        std::cout << "Residence Type: Hostel\n";
        std::cout << "Residential Area: " << residentialArea << std::endl;
        std::cout << "State: " << state << std::endl;
        if (roomSharingPreference != "") {
            std::cout << "Room Sharing Preference: " << roomSharingPreference << std::endl;
        }
    }

    calculateFee();  // Display fee information
}

void Student::calculateFee() const {
    std::cout << "\nFee Information:\n";
    std::cout << "---------------------------------------------" << std::endl;
    if (branch == "Computer Science") {
        std::cout << "Tuition Fee:      $10,000\n";
        std::cout << "Library Fee:      $500\n";
        std::cout << "Total Fee:        $10,500\n";
    } else if (branch == "Electrical Engineering") {
        std::cout << "Tuition Fee:      $9,500\n";
        std::cout << "Lab Fee:          $1,000\n";
        std::cout << "Total Fee:        $10,500\n";
    } else if (branch == "Mechanical Engineering") {
        std::cout << "Tuition Fee:      $9,000\n";
        std::cout << "Workshop Fee:     $1,500\n";
        std::cout << "Total Fee:        $10,500\n";
    } else if (branch == "Civil Engineering") {
        std::cout << "Tuition Fee:      $8,500\n";
        std::cout << "Project Fee:      $2,000\n";
        std::cout << "Total Fee:        $10,500\n";
    }

    // Additional fees for residence
    if (residenceType == "Bus") {
        std::cout << "Bus Fee:          $1,000\n";
    } else if (residenceType == "Hostel") {
        std::cout << "Hostel Fee:       $2,000\n";

        // Additional fees based on room sharing preference
        if (roomSharingPreference == "2 Sharing") {
            std::cout << "2 Sharing Fee:    $500\n";
        } else if (roomSharingPreference == "4 Sharing") {
            std::cout << "4 Sharing Fee:    $300\n";
        } else if (roomSharingPreference == "6 Sharing") {
            std::cout << "6 Sharing Fee:    $200\n";
        }
    }

    std::cout << "---------------------------------------------" << std::endl;
}

int main() {
    std::cout << "------------------Welcome to SRM AP UNIVERSITY------------------" << std::endl;
    std::cout << "________________Thanks for choosing our college______________" << std::endl;
    std::cout << "----------------------First step to the future-------------------" << std::endl;
    std::cout << "------------------------------------------------------------------" << std::endl;
    Student student;

    // Get student details
    student.setStudentDetails();

    // Check eligibility
    if (student.checkEligibility()) {
        // Eligible to choose a branch
        student.chooseBranch();

        // Choose residence type
        student.chooseResidenceType();

        // Provide residence details
        student.provideResidenceDetails();

        // Generate roll number and email ID
        student.generateRollNumberAndEmail();

        // Display information
        student.displayInformation();
    } else {
        std::cout << "\nSorry, you are not eligible for admission.\n";
    }

    return 0;
}
