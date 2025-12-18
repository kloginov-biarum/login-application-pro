# Bugs for Testing Training

This document describes intentional bugs introduced in the Sales Dashboard (`sales1` user) for software testing training purposes.

## Test User Credentials
- **Username**: `sales1`
- **Password**: `sales123`

## List of Intentional Bugs

### Bug #1: Incorrect Progress Percentage Calculation
**Location**: Sales Dashboard - Progress Bar

**Description**: 
The progress percentage is calculated incorrectly. Instead of calculating `(current / target) * 100`, it calculates `(target / current) * 100`.

**Expected Behavior**:
- Current: $32,500
- Target: $50,000
- Expected percentage: (32,500 / 50,000) * 100 = **65%**

**Actual Behavior**:
- Calculated percentage: (50,000 / 32,500) * 100 = **154%** (which exceeds 100% and is incorrect)

**How to Find**:
- Login as `sales1` / `sales123`
- Check the progress percentage displayed
- Verify the calculation manually

---

### Bug #2: Incorrect Remaining Amount Calculation
**Location**: Sales Dashboard - Stats Grid - "Remaining" card

**Description**:
The remaining amount is calculated by subtracting target from current instead of current from target, resulting in a negative value.

**Expected Behavior**:
- Remaining = Target - Current = $50,000 - $32,500 = **$17,500**

**Actual Behavior**:
- Remaining = Current - Target = $32,500 - $50,000 = **-$17,500** (negative value)

**How to Find**:
- Check the "Remaining" card in the stats grid
- Notice the negative value or incorrect calculation

---

### Bug #3: Incorrect Average Ticket Calculation
**Location**: Sales Dashboard - Sales Breakdown - "Average Ticket"

**Description**:
The average ticket is calculated by dividing current sales by the number of Personal Training sessions (15) instead of dividing by the number of Memberships Sold (23).

**Expected Behavior**:
- Average Ticket = Current Sales / Memberships Sold = $32,500 / 23 = **$1,413**

**Actual Behavior**:
- Average Ticket = Current Sales / Personal Training = $32,500 / 15 = **$2,167** (incorrect)

**How to Find**:
- Check the "Average Ticket" value in Sales Breakdown section
- Verify it should be calculated based on Memberships Sold, not Personal Training

---

## Testing Scenarios

### Scenario 1: Functional Testing
1. Login as `sales1` / `sales123`
2. Navigate to Sales Dashboard
3. Verify all displayed values are correct
4. Check calculations manually

### Scenario 2: Boundary Testing
1. Test with different sales values
2. Check what happens when current exceeds target
3. Verify percentage doesn't exceed 100%

### Scenario 3: Data Validation Testing
1. Verify all numbers are positive (except where negative makes sense)
2. Check that percentages are between 0-100%
3. Verify calculations match expected formulas

### Scenario 4: UI/UX Testing
1. Check if negative values are displayed correctly
2. Verify progress bar doesn't exceed 100% width
3. Check if incorrect calculations are visually obvious

## Expected Test Results

A good test should identify:
- ✅ Progress percentage showing 154% instead of 65%
- ✅ Remaining amount showing negative value (-$17,500)
- ✅ Average Ticket showing $2,167 instead of $1,413
- ✅ Progress bar extending beyond 100% width (if CSS allows)

## Notes for Instructors

These bugs are intentionally subtle and require:
- Manual calculation verification
- Understanding of business logic
- Attention to detail
- Knowledge of expected formulas

Students should practice:
- Writing test cases
- Manual testing
- Bug reporting
- Verification of calculations

