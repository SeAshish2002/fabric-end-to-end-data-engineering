## Metadata-Driven Ingestion Framework

The ingestion pipeline uses a metadata-driven orchestration framework implemented using:

- Lookup activity
- ForEach activity
- Dynamic parameter passing
- API-based ingestion
- Delete-if-exists logic
- Copy Activity execution

Pipeline Flow:

```text
Metadata JSON
      ↓
Lookup Activity
      ↓
ForEach Iteration
      ↓
Delete Existing Files
      ↓
Copy Activity (API Ingestion)
      ↓
Bronze Lakehouse
```

Advantages:

- Dynamic ingestion execution
- Reusable pipeline logic
- Reduced hardcoding
- Easier scalability
- Centralized metadata control