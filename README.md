    #include <iostream>
    #include <vector>
    #include <string>

    using namespace std;

    // Define a struct to represent a symptom
      struct Symptom {
    string name;
    int severity; // You can adjust the severity scale as needed
    };

      // Define a struct to represent a patient
    struct Patient {
    vector<Symptom> symptoms;
    };

    // Function to predict diseases based on symptoms
    string predictDisease(const Patient& patient) {
    // Perform disease prediction logic here
    // This could involve querying a medical database or using machine learning models

    // For now, let's just return a placeholder result
    return "Placeholder disease prediction";
    }

      int main() {
    cout << "Welcome to Disease Predictor" << endl;
    cout << "Please enter the symptoms one by one. Type 'done' when finished." << endl;

    vector<Symptom> symptoms;
    bool doneEnteringSymptoms = false;

    while (!doneEnteringSymptoms) {
        cout << "Enter symptom name:" << endl;
        string symptomName;
        getline(cin, symptomName);

        if (!symptomName.empty()) {
            if (symptomName == "done") {
                doneEnteringSymptoms = true;
            } else {
                cout << "Enter symptom severity (1-10):" << endl;
                int severity;
                cin >> severity;
                cin.ignore(); // Clear input buffer

                // Create the symptom and add it to the vector
                Symptom symptom = {symptomName, severity};
                symptoms.push_back(symptom);
            }
        } else {
            cout << "Invalid input. Please enter a symptom name." << endl;
        }
    }

    Patient patient = {symptoms};
    string predictedDisease = predictDisease(patient);
    cout << "Predicted disease based on entered symptoms: " << predictedDisease << endl;

    return 0;
}
