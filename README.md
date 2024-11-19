- 👋 Hi, I’m @matei2407
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
matei2407/matei2407 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
---#include <string.h>

int maxCost(int cost_count, int* cost, int labels_count, char** labels, int dailyCount) {
    int max_cost = 0;  // To store the maximum cost encountered on any day
    int current_cost = 0;  // To track the cost of the current day
    int legal_count = 0;  // To track the number of "legal" laptops for the current day

    for (int i = 0; i < cost_count; i++) {
        // Add the cost of the current laptop
        current_cost += cost[i];

        // Increment the legal laptop count if the label is "legal"
        if (strcmp(labels[i], "legal") == 0) {
            legal_count++;
        }

        // Check if the dailyCount of legal laptops has been met
        if (legal_count == dailyCount) {
            // Update the maximum cost if this day's cost is higher
            if (current_cost > max_cost) {
                max_cost = current_cost;
            }

            // Reset for the next day
            current_cost = 0;
            legal_count = 0;
        }
    }

    return max_cost;
}
