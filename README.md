def vacuum_cleaner():
    # Initial environment setup
    environment = {}
    environment['A'] = input("Enter status of Room A (clean/dirty): ").strip().lower()
    environment['B'] = input("Enter status of Room B (clean/dirty): ").strip().lower()
    
    # Initial position of vacuum
    vacuum_pos = input("Enter starting position of Vacuum (A/B): ").strip().upper()
    
    print("\n--- Simulation Start ---")
    print("Initial Environment:", environment, " | Vacuum at:", vacuum_pos)
    
    # Cleaning process
    if environment[vacuum_pos] == "dirty":
        print(f"Vacuum in Room {vacuum_pos} | Status: Dirty → Cleaned ✅")
        environment[vacuum_pos] = "clean"
    else:
        print(f"Vacuum in Room {vacuum_pos} | Status: Already Clean → No action")
    
    # Move to the other room
    if vacuum_pos == "A":
        vacuum_pos = "B"
    else:
        vacuum_pos = "A"
    
    if environment[vacuum_pos] == "dirty":
        print(f"Vacuum moved to Room {vacuum_pos} | Status: Dirty → Cleaned ✅")
        environment[vacuum_pos] = "clean"
    else:
        print(f"Vacuum moved to Room {vacuum_pos} | Status: Already Clean → No action")
    
    print("\nFinal Environment:", environment)
    print("✅ Both rooms are clean now!")


if __name__ == "__main__":
    vacuum_cleaner()
