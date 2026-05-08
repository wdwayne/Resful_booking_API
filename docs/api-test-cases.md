| Test ID    | Endpoint             | Scenario               | Expected Result      |
| ---------- | -------------------- | ---------------------- | -------------------- |
| API-TC-001 | POST /auth           | Valid login            | Token returned       |
| API-TC-002 | POST /auth           | Invalid credentials    | 200 with reason fail |
| API-TC-003 | POST /booking        | Create booking         | Booking ID returned  |
| API-TC-004 | PUT /booking/{id}    | Update booking         | Booking updated      |
| API-TC-005 | DELETE /booking/{id} | Delete booking         | 201 returned         |
| API-TC-006 | DELETE /booking/{id} | Delete invalid booking | 405 returned         |