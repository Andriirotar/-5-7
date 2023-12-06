#include <iostream>
#include <vector>
#include <string>
class BOOK {
private:
    std::string Name;
    std::string Avtor;
    std::string Data;
    double Cost;
public:
    BOOK() : Cost(0.0) {}
    BOOK(const std::string& name, const std::string& avtor, const std::string& data, double cost)
        : Name(name), Avtor(avtor), Data(data), Cost(cost) {}
    // Методи для доступу до полів класу

    std::string getName() const {
        return Name;
    }
    std::string getAvtor() const {
        return Avtor;
    }
    std::string getData() const {
        return Data;
    }
    double getCost() const {
        return Cost;
    }
};
int main() {
    const int N = 3; // Вказати кількість книг
    std::vector<BOOK> SHOP(N);
    // Введення даних з клавіатури
    for (int i = 0; i < N; ++i) {
        std::string name, avtor, data;
        double cost;
        std::cout << "Введіть відомості про книгу " << i + 1 << ":\n";
        std::cout << "Ім'я: "; std::cin >> name;
        std::cout << "Автор: "; std::cin >> avtor;
        std::cout << "Дата: "; std::cin >> data;
        std::cout << "Вартість: "; std::cin >> cost;
        SHOP[i] = BOOK(name, avtor, data, cost);
    }
    // Виведення книг, надрукованих в заданому році (наприклад, 2022)
    std::string desiredYear = "2022";
    std::cout << "\nBooks printed in " << desiredYear << ":\n";
    for (const auto& book : SHOP) {
        if (book.getData().find(desiredYear) != std::string::npos) {
            std::cout << "Name: " << book.getName() << ", Author: " << book.getAvtor() << ", Date: " << book.getData() << ", Cost: " << book.getCost() << "\n";
        }
    }
    return 0;
}
