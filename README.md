![image](https://github.com/SOEN345-WINTER2024/logic-coverage-lab-HoangMinhKhoiPham/assets/97756628/f39ceb11-c5ea-4c4f-9ecb-386104c32377)# Hoang Minh Khoi Pham - 40162551

Step 1: Logic Expression - (a || (b && c)

Step 2: Get Predicate Coverage: 
1. p = true:
   - a=true
   - b=true / c = true
2. p = false
   - a= false
   - b = false/ c= false
Step 3: Clause Coverage
<img width="691" alt="Screenshot 2024-03-15 at 12 30 33 PM" src="https://github.com/SOEN345-WINTER2024/logic-coverage-lab-HoangMinhKhoiPham/assets/97756628/20ac6f75-b457-4174-b67d-bd92765b5df5">

Step 4: Combinatorial Coverage
<img width="475" alt="Screenshot 2024-03-15 at 12 37 27 PM" src="https://github.com/SOEN345-WINTER2024/logic-coverage-lab-HoangMinhKhoiPham/assets/97756628/517e2ac2-9858-462b-902c-b3343b1c88f6">

Step 5: CACC
<img width="1352" alt="Screenshot 2024-03-15 at 12 37 45 PM" src="https://github.com/SOEN345-WINTER2024/logic-coverage-lab-HoangMinhKhoiPham/assets/97756628/cf1ba5d2-ac2b-44f8-89d7-8ac07caf263d">

Step 6: RACC
<img width="1350" alt="Screenshot 2024-03-15 at 12 38 10 PM" src="https://github.com/SOEN345-WINTER2024/logic-coverage-lab-HoangMinhKhoiPham/assets/97756628/1063d26b-73b9-4ab6-a211-e854a3b757c6">

JUnit Predicate Coverage
```
public class PredicateCoverageTest {
    @Test
    public void testTTT() {
        assertTrue(evaluateExpression(true, true, true));
    }
    @Test
    public void testFFF() {
        assertFalse(evaluateExpression(false, false, false));
    }
}
```

Junit Coverage:
```
public class ClauseCoverageTest {
    @Test
    public void testAllTrue() {
        assertTrue(evaluateExpression(true, true, true));
    }
    @Test
    public void testAFalse() {
        assertFalse(evaluateExpression(false, true, true));
    }
}
```

Junit CACC
```
public class RACCTest {

    // Test case for pair (1, 5)
    @Test
    public void testPair1() {
        assertTrue(evaluateExpression(true, true, true));  // Decision 1 is true
        assertFalse(evaluateExpression(true, false, true)); // Decision 5 is false
    }

    // Test case for pair (1, 6)
    @Test
    public void testPair2() {
        assertTrue(evaluateExpression(true, true, true));  // Decision 1 is true
        assertFalse(evaluateExpression(false, true, true)); // Decision 6 is false
    }

    // Test case for pair (1, 7)
    @Test
    public void testPair3() {
        assertTrue(evaluateExpression(true, true, true));  // Decision 1 is true
        assertFalse(evaluateExpression(false, false, true)); // Decision 7 is false
    }

    // Test case for pair (2, 5)
    @Test
    public void testPair4() {
        assertTrue(evaluateExpression(true, true, false));  // Decision 2 is true
        assertFalse(evaluateExpression(true, false, true)); // Decision 5 is false
    }

    // Test case for pair (2, 6)
    @Test
    public void testPair5() {
        assertTrue(evaluateExpression(true, true, false));  // Decision 2 is true
        assertFalse(evaluateExpression(false, true, true)); // Decision 6 is false
    }

    // Test case for pair (2, 7)
    @Test
    public void testPair6() {
        assertTrue(evaluateExpression(true, true, false));  // Decision 2 is true
        assertFalse(evaluateExpression(false, false, true)); // Decision 7 is false
    }

    // Test case for pair (3, 5)
    @Test
    public void testPair7() {
        assertTrue(evaluateExpression(true, false, true));  // Decision 3 is true
        assertFalse(evaluateExpression(true, false, true)); // Decision 5 is false
    }

    // Test case for pair (3, 6)
    @Test
    public void testPair8() {
        assertTrue(evaluateExpression(true, false, true));  // Decision 3 is true
        assertFalse(evaluateExpression(false, true, true)); // Decision 6 is false
    }

    // Test case for pair (3, 7)
    @Test
    public void testPair9() {
        assertTrue(evaluateExpression(true, false, true));  // Decision 3 is true
        assertFalse(evaluateExpression(false, false, true)); // Decision 7 is false
    }
}
```
Junit RACC:
```
public class RACCTest {
// Test cases for the pairs (1, 5), (1, 6), (1, 7)
    @Test
    public void testPair1() {
        assertTrue(evaluateExpression(true, true, true));
        assertFalse(evaluateExpression(true, false, true)); 
    }
    @Test
    public void testPair2() {
        assertTrue(evaluateExpression(true, true, false));
        assertFalse(evaluateExpression(false, true, false));
    }
    @Test
    public void testPair3() {
        assertTrue(evaluateExpression(true, false, true));
        assertFalse(evaluateExpression(false, false, true));
    }
}
```
Step 7:
```
Pc = (Pc=true + Pb=true) + (Pc=false + Pb=true) + (Pc=true + Pb=false) + (Pc=false + Pb=false)
   = !a && b
```
