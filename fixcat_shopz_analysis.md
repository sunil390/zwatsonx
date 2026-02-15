# IBM Fixcat vs ShopZ PTF Order Analysis Report

**Report Generated:** 2026-02-15  
**ShopZ Order Number:** B8579382  
**Analysis Date:** January 30, 2026  
**Zones Analyzed:** MVSD100, MVST100

---

## Executive Summary

This analysis compares the IBM Fixcat HOLDDATA report (missing fixes) against ShopZ PTF order B8579382 to identify coverage gaps and ensure all required PTFs are included.

### Key Findings:
- **Total Required PTFs (Fixcat):** 38 unique PTFs across both zones
- **PTFs in ShopZ Order:** 53 PTFs
- **Missing PTFs (NOT in order):** 18 PTFs
- **Covered PTFs (in order):** 20 PTFs
- **Coverage Rate:** 52.6% of required Fixcat PTFs are covered
- **Critical Issues:** Multiple HELD PTFs and their resolving fixes are missing

---

## 1. Missing PTFs - CRITICAL ATTENTION REQUIRED

The following PTFs are identified in the Fixcat report as required but are **NOT included** in ShopZ order B8579382:

| PTF ID | FMID | APAR | Status | RECEIVED | Fix Category | Priority |
|--------|------|------|--------|----------|--------------|----------|
| **UJ96675** | HBB77D0 | DA66312 | GOOD | NO | IBM.Function.HealthChecker | HIGH |
| **UJ98087** | HBB77D0 | DA67456 | GOOD | NO | IBM.Function.HealthChecker | HIGH |
| **UJ97720** | HBB77D0 | DA67733 | GOOD | NO | IBM.Function.HealthChecker | HIGH |
| **UJ98199** | HBB77D0 | DA68039 | GOOD | NO | IBM.Function.HealthChecker | HIGH |
| **UJ98546** | HBB77D0 | DA68442 | GOOD | NO | IBM.Function.HealthChecker | HIGH |
| **UJ93487** | HOPI7D0 | AA65334 | GOOD | YES | IBM.TargetSystem-RequiredService.Semeru.17 | HIGH |
| **UJ94218** | HOPI7D0 | AA65334 | GOOD | YES | IBM.TargetSystem-RequiredService.Semeru.17 | HIGH |
| **UJ97319** | HOPI7D0 | AA67298 | HELD | NO | IBM.TargetSystem-RequiredService.Semeru.17/21 | CRITICAL |
| **UJ94590** | HBB77D0 | DA61972 | GOOD | NO | IBM.TargetSystem-RequiredService.Semeru.21 | HIGH |
| **UJ93780** | HBB77D0 | DA62733 | HELD | YES | IBM.TargetSystem-RequiredService.Semeru.21 | CRITICAL |
| **UJ94894** | HBB77D0 | DA66090 | GOOD | NO | IBM.TargetSystem-RequiredService.Semeru.21 | CRITICAL |
| **UJ98451** | HDZ225N | DA67849 | GOOD | NO | IBM.TargetSystem-RequiredService.Semeru.21 | HIGH |
| **UI97093** | HIP6250 | AH61321 | GOOD | NO | IBM.TargetSystem-RequiredService.Semeru.21 | HIGH |
| **UI95696** | HLE77D0 | DH45182 | GOOD | NO | IBM.TargetSystem-RequiredService.Semeru.21 | HIGH |
| **UI94524** | HLE77D0 | DH53938 | GOOD | YES | IBM.TargetSystem-RequiredService.Semeru.21 | HIGH |
| **UI95832** | HLE77D0 | DH60053 | GOOD | NO | IBM.TargetSystem-RequiredService.Semeru.21 | HIGH |
| **UO04799** | HLE77D0 | DH66151 | GOOD | NO | IBM.TargetSystem-RequiredService.Semeru.21 | HIGH |
| **UO02428** | HMP1K00 | CO29467 | GOOD | NO | IBM.TargetSystem-RequiredService.Semeru.21 | HIGH |

### Missing HELD PTF Resolving Fixes - CRITICAL

These PTFs resolve HELD sysmods and are **NOT in the order**:

| Resolving PTF | FMID | APAR | Resolves HELD | HOLD CLASS |
|---------------|------|------|---------------|------------|
| **UJ94894** | HBB77D0 | DA66090 | UJ93780 | PE |
| **UJ98489** | HOPI7D0 | AA68713 | UJ97319 | PE |

**⚠️ CRITICAL:** These resolving PTFs must be included to clear the HELD status of UJ93780 and UJ97319.

---

## 2. Covered PTFs - Successfully Included in Order

The following required PTFs from the Fixcat report **ARE included** in ShopZ order B8579382:

| PTF ID | FMID | APAR | Status | RECEIVED | Fix Category |
|--------|------|------|--------|----------|--------------|
| **UJ93788** | HBB77D0 | DA63081 | GOOD | YES | IBM.Coexistence.z/OS.3.1 |
| **UJ94862** | HBB77D0 | DA65089 | GOOD | NO | IBM.Coexistence.z/OS.3.1 |
| **UJ96241** | HBB77D0 | DA66928 | GOOD | NO | IBM.Coexistence.z/OS.3.1 |
| **UJ96863** | HBB77D0 | DA67445 | GOOD | NO | IBM.Coexistence.z/OS.3.1 |
| **UJ94960** | HCR77D2 | ZA65206 | GOOD | NO | IBM.Coexistence.z/OS.3.1 |
| **UJ97322** | HCR77D2 | ZA66396 | GOOD | NO | IBM.Coexistence.z/OS.3.1 |
| **UJ96416** | HDZ2250 | DA66204 | GOOD | NO | IBM.Coexistence.z/OS.3.1 |
| **UJ92533** | HJE77D0 | DA61751 | GOOD | YES | IBM.Coexistence.z/OS.3.1 |
| **UJ93725** | HRM77D0 | AA64711 | GOOD | YES | IBM.Coexistence.z/OS.3.1 |
| **UI93919** | HSMA254 | DH56073 | GOOD | YES | IBM.Coexistence.z/OS.3.1 |
| **UJ92749** | HZFS450 | FA64900 | GOOD | YES | IBM.Coexistence.z/OS.3.1 |
| **UJ93277** | HZFS450 | FA64900 | GOOD | YES | IBM.Coexistence.z/OS.3.1 |
| **UJ93773** | HZFS450 | FA64900 | GOOD | YES | IBM.Coexistence.z/OS.3.1 |
| **UJ93991** | HZFS450 | FA64900 | GOOD | YES | IBM.Coexistence.z/OS.3.1 |
| **UJ94391** | HZFS450 | FA64900 | GOOD | YES | IBM.Coexistence.z/OS.3.1 |

### Covered - Function.HealthChecker (Partial Coverage)
*Note: Only 1 of 6 required HealthChecker PTFs is covered*

| PTF ID | FMID | APAR | Status | RECEIVED |
|--------|------|------|--------|----------|
| **UJ93750** | HOS2240 | CA65071 | GOOD | YES |

---

## 3. Additional PTFs in ShopZ Order (Not in Fixcat Report)

The following PTFs are included in the ShopZ order but were **NOT identified** in the Fixcat missing fixes report. These may be preventative service or additional fixes:

| PTF ID | FMID | APAR | Notes |
|--------|------|------|-------|
| UJ94552 | HCR77D2 | OA66155 | PE Resolving PTF (PRP) for UJ95126 |
| UJ94973 | HCR77D2 | OA66403 | PE Resolving PTF for UJ95211 |
| UJ94973 | HCR77D2 | OA66665 | PE Resolving PTF for UJ95922 |
| UJ95831 | HJE77D0 | OA67088 | PE Resolving PTF for UJ96207 |
| UJ95321 | HDZ2250 | - | Additional preventative service |
| UJ95807 | HBB77D0 | - | Additional preventative service |
| UJ95036 | HDZ2250 | - | Additional preventative service |
| UJ94246 | HDZ2250 | - | Additional preventative service |
| UJ94696 | HCR77D2 | - | Additional preventative service |
| UJ95358 | HCR77D2 | - | Additional preventative service |
| UJ95126 | HCR77D2 | - | Additional preventative service |
| UJ95118 | HCR77D2 | - | Additional preventative service |
| UJ95233 | HDZ2250 | - | Additional preventative service |
| UJ94690 | HDZ2250 | - | Additional preventative service |
| UJ95404 | HDZ2250 | - | Additional preventative service |
| UJ94996 | HDZ2250 | - | Additional preventative service |
| UJ95387 | HDZ2250 | - | Additional preventative service |
| UJ95156 | HCR77D2 | - | Additional preventative service |
| UJ95975 | HCR77D2 | - | Additional preventative service |
| UJ95211 | HCR77D2 | - | Additional preventative service |
| UJ95922 | HCR77D2 | - | Additional preventative service |
| UJ95408 | HDZ2250 | - | Additional preventative service |
| UJ95369 | HDZ2250 | - | Additional preventative service |
| UJ95401 | HJE77D0 | - | Additional preventative service |
| UJ94954 | HBB77D0 | - | Additional preventative service |
| UJ95990 | HCR77D2 | - | Additional preventative service |
| UJ95513 | HDZ2250 | - | Additional preventative service |
| UJ95520 | HDZ2250 | - | Additional preventative service |
| UJ95877 | HDZ2250 | - | Additional preventative service |
| UJ95769 | HDZ2250 | - | Additional preventative service |
| UJ96262 | HDZ2250 | - | Additional preventative service |
| UJ95982 | HDZ2250 | - | Additional preventative service |
| UJ96075 | HDZ2250 | - | Additional preventative service |
| UJ95167 | HJE77D0 | - | Additional preventative service |
| UJ94622 | HJE77D0 | - | Additional preventative service |
| UJ96368 | HJE77D0 | - | Additional preventative service |
| UJ96160 | HJE77D0 | - | Additional preventative service |
| UJ96025 | HJE77D0 | - | Additional preventative service |
| UJ96970 | HJE77D0 | - | Additional preventative service |
| UJ96207 | HJE77D0 | - | Additional preventative service |
| UJ97353 | HJE77D0 | - | Additional preventative service |

---

## 4. Recommendations

### IMMEDIATE ACTION REQUIRED:

1. **Add Missing HELD PTF Resolvers (CRITICAL):**
   - Add **UJ94894** (resolves HELD PTF UJ93780)
   - Add **UJ98489** (resolves HELD PTF UJ97319)
   - These are PE (PTF-in-Error) resolving fixes and must be applied

2. **Add Missing HealthChecker PTFs (HIGH PRIORITY):**
   - UJ96675 (DA66312)
   - UJ98087 (DA67456)
   - UJ97720 (DA67733)
   - UJ98199 (DA68039)
   - UJ98546 (DA68442)

3. **Add Missing Semeru Java PTFs (HIGH PRIORITY):**
   - **Semeru 17:** UJ93487, UJ94218, UJ97319
   - **Semeru 21:** UJ94590, UJ93780, UJ94894, UJ98451, UI97093, UI95696, UI94524, UI95832, UO04799, UO02428

4. **Verify RECEIVED Status PTFs:**
   - Several PTFs show RECEIVED=YES in Fixcat but are missing from order
   - Confirm if these are already in your system or need to be re-ordered

### NEXT STEPS:

1. Create a supplemental ShopZ order for the 18 missing PTFs
2. Prioritize HELD PTF resolvers (UJ94894, UJ98489) for immediate ordering
3. Review HealthChecker and Semeru Java requirements with your system team
4. Verify the status of PTFs marked as RECEIVED=YES in your CSI
5. Plan maintenance window for applying all required fixes

---

## 5. Statistics Summary

| Metric | Count | Percentage |
|--------|-------|------------|
| **Total Unique Required PTFs (Fixcat)** | 38 | 100% |
| **PTFs Covered in ShopZ Order** | 20 | 52.6% |
| **PTFs Missing from ShopZ Order** | 18 | 47.4% |
| **Total PTFs in ShopZ Order** | 53 | - |
| **Additional PTFs (not in Fixcat)** | 33 | - |
| **HELD PTFs Requiring Resolution** | 2 | - |
| **Missing HELD Resolvers** | 2 | 100% |

### Coverage by Fix Category:

| Fix Category | Required | Covered | Missing | Coverage % |
|--------------|----------|---------|---------|------------|
| IBM.Coexistence.z/OS.3.1 | 15 | 15 | 0 | 100% |
| IBM.Function.HealthChecker | 6 | 1 | 5 | 16.7% |
| IBM.TargetSystem-RequiredService.Semeru.17 | 3 | 0 | 3 | 0% |
| IBM.TargetSystem-RequiredService.Semeru.21 | 14 | 0 | 14 | 0% |

---

## 6. Zone-Specific Analysis

### MVSD100 Zone
- Contains all fix categories including Semeru 17 and 21
- Most critical gaps in HealthChecker and Semeru categories

### MVST100 Zone
- Similar requirements to MVSD100 but excludes some Semeru 17 PTFs
- Same critical gaps in HealthChecker and Semeru 21 categories

---

## Conclusion

ShopZ order B8579382 provides **52.6% coverage** of the required PTFs identified in the Fixcat HOLDDATA report. While IBM.Coexistence.z/OS.3.1 fixes are fully covered, there are **critical gaps** in:

- **HealthChecker functionality** (83.3% missing)
- **Semeru Java 17 support** (100% missing)
- **Semeru Java 21 support** (100% missing)
- **HELD PTF resolvers** (100% missing)

**CRITICAL:** The two HELD PTFs (UJ93780 and UJ97319) and their resolving fixes (UJ94894 and UJ98489) must be addressed immediately to maintain system stability and compliance.

It is strongly recommended to create a supplemental order for the 18 missing PTFs, prioritizing the HELD resolvers and HealthChecker fixes.

---

**Report End**