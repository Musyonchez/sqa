# Smart Study Group Matching System

## 📋 What it is
A system that automatically forms study groups based on students' courses, strengths, weaknesses, and availability.

## ✨ Features
Students select:
- Units they are taking
- Topics they find difficult
- Available study times

System capabilities:
- Matches students into balanced groups
- Suggests meeting schedule
- Tracks participation

## 🎯 Why This is Great
It has matching rules and constraints — excellent for verification.

## 🧪 What You Can Test

### Functional Testing
- **Correct matching based on same course**: Verify students are only grouped with others taking the same units
- **No student assigned to two groups at same time**: Ensure no scheduling conflicts for individual students
- **Handling odd number of students**: Test system behavior when groups can't be evenly divided
- **Time conflict detection**: Validate that the system properly identifies and handles scheduling conflicts

### Non-Functional Testing
- **System performance with many users**: Load testing to ensure the matching algorithm scales efficiently

## 🔍 Test Scenarios

### Scenario 1: Basic Matching
- **Given**: 6 students enrolled in "Software Quality Assurance"
- **When**: All students mark "Test Automation" as a difficult topic
- **Then**: System should form 2 groups of 3 students each

### Scenario 2: Time Conflict Prevention
- **Given**: Student A is already in a study group meeting Monday 2-4 PM
- **When**: System tries to assign Student A to another group with same time slot
- **Then**: System should reject the assignment and flag the conflict

### Scenario 3: Odd Number Handling
- **Given**: 7 students need to be grouped (target group size: 3)
- **When**: Matching algorithm runs
- **Then**: System should create 2 groups of 3 and 1 group of 4 (or similar balanced distribution)

### Scenario 4: No Common Availability
- **Given**: Students have completely non-overlapping schedules
- **When**: System attempts to match them
- **Then**: System should notify that no suitable meeting time exists

### Scenario 5: Load Testing
- **Given**: 1000+ students with various courses and availability
- **When**: Matching algorithm executes
- **Then**: System should complete matching within acceptable time limit (e.g., < 30 seconds)

## 📊 Verification Points

### Matching Rules
1. ✅ Students must share at least one common course
2. ✅ Groups should have complementary strengths/weaknesses
3. ✅ All group members must have overlapping availability
4. ✅ Group size should be within defined limits (e.g., 3-5 students)

### Constraints
1. 🚫 No student in multiple groups with overlapping times
2. 🚫 No groups with zero common availability
3. 🚫 No groups exceeding maximum size
4. 🚫 No groups below minimum size (unless unavoidable)

## 🛠️ Technical Considerations

### Data Requirements
- Student profiles (ID, name, courses)
- Course enrollment data
- Availability schedules (time slots)
- Topic difficulty ratings
- Group size parameters

### Edge Cases to Test
- Single student in a course
- All students available at different times
- Students with identical profiles
- Maximum capacity scenarios
- Concurrent matching requests
- Database connection failures
- Invalid input data

## 📈 Success Metrics
- **Match Success Rate**: % of students successfully placed in groups
- **Satisfaction Score**: Student feedback on group compatibility
- **Time Efficiency**: Average time to generate matches
- **Conflict Rate**: % of scheduling conflicts detected and prevented
- **Participation Rate**: % of students actively using matched groups
