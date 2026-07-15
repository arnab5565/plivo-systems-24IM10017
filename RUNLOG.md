# Experiment Log

| Profile | `delay_ms` | Miss % | Overhead | Changes / Rationale |
|---------|------------|--------|----------|---------------------|
| A.json  | 60 ms      | 0.73%  | 1.98x    | Initial implementation of hybrid FEC + ARQ. 60ms is the minimum safe delay for max 40ms jitter + 20ms FEC offset. |
| B.json  | 85 ms      | 3.27%  | 1.98x    | Tested 85ms on B to find absolute lowest. Resulted in high misses because max jitter is 80ms, so 100ms+ is required to safely receive `dup_offset=1`. |
| B.json  | 100 ms     | 1.40%  | 1.98x    | Increased to 100ms. Still slightly > 1.0% due to floating point timing edge cases when packets arrive exactly on the deadline. |
| B.json  | 105 ms     | 0.60%  | 1.98x    | Increased to 105ms. Achieved VALID run. This provides a 5ms safety buffer for packet scheduling. |

**Final Lock-in**: `delay_ms = 105`
