This exam is based on the principles of software testing as outlined in Chapter 8 of the provided Software Engineering material. It is designed at a difficult college level to test deep understanding of testing strategies, processes, and goals.

---

### **Software Engineering: Chapter 8 - Software Testing Exam**

**Total Questions:** 40

**Format:** Multiple Choice (MCQ) and True/False

---

#### **Section 1: Multiple Choice (Select the best answer)**

1. **What is the primary distinction between "Verification" and "Validation"?**
    
    - A. Verification asks "Are we building the right product?", while Validation asks "Are we building the product right?"
        
    - B. Verification asks "Are we building the product right?", while Validation asks "Are we building the right product?"
        
    - C. Verification is a dynamic process, while Validation is purely static.
        
    - D. Verification is performed by users, while Validation is performed by developers.
        
2. **Which of the following is an advantage of software inspections over dynamic testing?**
    
    - A. Inspections can check non-functional characteristics like performance.
        
    - B. Inspections require a fully executable system to be effective.
        
    - C. Errors do not "mask" other errors during a static inspection.
        
    - D. Inspections are only useful for finding defects in code, not requirements.
        
3. **In the context of Test-Driven Development (TDD), what is the "critical driver" of development?**
    
    - A. Completing the code before the deadline.
        
    - B. Ensuring all code is written by a single senior developer.
        
    - C. Passing the tests that were written before the code.
        
    - D. Minimizing the number of automated tests.
        
4. **Which testing level focuses specifically on testing component interfaces to detect faults due to invalid assumptions?**
    
    - A. Unit testing
        
    - B. Component testing
        
    - C. System testing
        
    - D. Acceptance testing
        
5. **When testing an object class, "complete test coverage" must include:**
    
    - A. Testing only the most frequently used methods.
        
    - B. Testing all operations, setting/interrogating all attributes, and exercising all states.
        
    - C. Automated tests for 50% of the code.
        
    - D. Only testing the public interface while ignoring private states.
        
6. **A "successful" defect test is defined as one that:**

    - A. Executes without any errors or warnings.
        
    - B. Proves the system meets all its requirements.
        
    - C. Makes the system perform incorrectly, thereby exposing a defect.
        
    - D. Is completed within the allocated budget.
        
7. **What is the primary objective of "Release Testing"?**
    
    - A. To discover as many bugs as possible (defect testing).
        
    - B. To convince the supplier/customer that the system is good enough for use (validation testing).
        
    - C. To allow developers to debug their own code.
        
    - D. To test individual units in isolation.
        
8. **Which type of interface error occurs when a calling component makes an error in the order of parameters?**
    
    - A. Interface misunderstanding
        
    - B. Timing error
        
    - C. Interface misuse
        
    - D. Shared memory corruption
        
9. **In an automated unit test framework (like JUnit), which part involves comparing the result of a call with the expected result?**
    
    - A. Setup part
        
    - B. Call part
        
    - C. Assertion part
        
    - D. Takedown part
        
10. **Regression testing is most accurately described as:**
    
    - A. Testing a system to see how it performs under heavy load.
        
    - B. Testing the system to ensure that changes have not "broken" previously working functionality.
        
    - C. Testing the system only when it is in a "regressive" or failing state.
        
    - D. A manual process used only during the requirement phase.
        
11. **Partition testing involves:**
    
    - A. Splitting the development team into different partitions.
        
    - B. Identifying groups of inputs with common characteristics that should be processed the same way.
        
    - C. Testing every possible input value in the system.
        
    - D. Dividing the software into different geographical releases.
        
12. **Stress testing is a form of:**
    
    - A. Unit testing
        
    - B. Performance testing
        
    - C. Alpha testing
        
    - D. Static verification
        
13. **Which testing strategy is based on previous experience of the kinds of errors programmers often make?**
    
    - A. Partition testing
        
    - B. Guideline-based testing
        
    - C. Requirements-based testing
        
    - D. Exhaustive testing
        
14. **What is a major difficulty when designing tests for object classes that use inheritance?**
    
    - A. The code is too short to test.
        
    - B. The information to be tested is not localized.
        
    - C. Automated tools cannot handle inheritance.
        
    - D. Objects cannot be tested in isolation.
        
15. **Which of the following is NOT a type of user testing?**
    
    - A. Alpha testing
        
    - B. Beta testing
        
    - C. Component testing
        
    - D. Acceptance testing
        
16. **System testing during development primarily focuses on:**
    
    - A. Individual methods.
        
    - B. Re-writing the system specification.
        
    - C. Interactions between components and emergent behavior.
        
    - D. Static analysis of the source code.
        
17. **Which type of testing is usually a "black-box" process where tests are derived solely from the specification?**
    
    - A. Unit testing
        
    - B. Release testing
        
    - C. Object class testing
        
    - D. TDD
        
18. **In agile methods, who is typically responsible for defining and making decisions on acceptance tests?**
    
    - A. The lead programmer
        
    - B. A separate QA team in another company
        
    - C. The user or customer who is part of the development team
        
    - D. The project manager
        
19. **If you are testing a "sequence" (like an array), a general guideline is to:**
    
    - A. Only test the middle element.
        
    - B. Test with sequences of zero length and sequences with only a single value.
        
    - C. Use the same size sequence for every test.
        
    - D. Avoid testing the first and last elements.
        
20. **Which statement about "V & V confidence" is true?**
    
    - A. The aim is to prove a program is 100% defect-free.
        
    - B. Marketing environment (e.g., getting to market early) can influence the required level of confidence.
        
    - C. All software requires the same level of confidence regardless of its purpose.
        
    - D. Confidence depends only on the number of testers.
        

---

#### **Section 2: True or False**

21. **True/False:** Program testing can demonstrate that a program is entirely free of remaining faults.
    
22. **True/False:** Development testing includes unit testing, component testing, and system testing.
    
23. **True/False:** In Test-Driven Development (TDD), you should implement the full functionality of a feature before writing any tests for it.
    
24. **True/False:** Software inspections are a form of dynamic verification because they involve executing the code.
    
25. **True/False:** For custom software, there should be at least one test for every requirement in the requirements document.
    
26. **True/False:** Beta testing involves users working with the development team at the developer’s site.
    
27. **True/False:** Interface misuse occurs when a calling component makes incorrect assumptions about the internal behavior of the called component.
    
28. **True/False:** A test suite for regression testing is developed incrementally during TDD.
    
29. **True/False:** Inspections can effectively check if a system conforms to its specification but cannot check non-functional characteristics like usability.
    
30. **True/False:** Performance tests should reflect the actual profile of use of the system.
    
31. **True/False:** Exhaustive system testing is generally possible for most modern software products.
    
32. **True/False:** Scenario testing involves inventing a typical usage scenario to derive test cases.
    
33. **True/False:** Unit testing is primarily a validation testing process, not a defect testing process.
    
34. **True/False:** Automated tests should be written and embedded in a program so they can be run every time a change is made.
    
35. **True/False:** Verification asks "Are we building the product right?"
    
36. **True/False:** In TDD, if a newly written test fails initially, it means the process has failed.
    
37. **True/False:** Alpha testing is performed by users at the developer's site.
    
38. **True/False:** Shared memory interfaces involve a block of memory being shared between procedures.
    
39. **True/False:** System testing should only be done by the individual who wrote the code for the components.
    
40. **True/False:** Acceptance testing is primarily used for generic software products sold on the open market.
    

---

### **Answer Key**

1. **B**
    
2. **C**
    
3. **C**
    
4. **B**
    
5. **B**
    
6. **C**
    
7. **B**
    
8. **C**
    
9. **C**
    
10. **B**
    
11. **B**
    
12. **B**
    
13. **B**
    
14. **B**
    
15. **C**
    
16. **C**
    
17. **B**
    
18. **C**
    
19. **B**
    
20. **B**
    
21. **False**
    
22. **True**
    
23. **False**
    
24. **False**
    
25. **True**
    
26. **False** (This is Alpha testing)
    
27. **False** (This is interface misunderstanding)
    
28. **True**
    
29. **True**
    
30. **True**
    
31. **False**
    
32. **True**
    
33. **False** (It is a defect testing process)
    
34. **True**
    
35. **True**
    
36. **False** (The test is expected to fail initially)
    
37. **True**
    
38. **True**
    
39. **False** (It is a collective process)
    
40. **False** (Primarily for custom systems)