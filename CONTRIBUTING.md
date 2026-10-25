# Contributing

Use the [source repository](https://github.com/mr-cache/mr-cache) for package changes and non-sensitive bug reports. Include a minimal reproduction, PHP/Illuminate/Redis/client versions, query shape with synthetic bindings, and whether transactions, replicas or external writers are involved. Never include credentials or customer rows.

Run in the source checkout:

```sh
composer validate --strict
composer install
composer lint
MRCACHE_TEST_REDIS_PORT=6379 composer test
MRCACHE_TEST_REDIS_PORT=6379 MRCACHE_TEST_REDIS_CLIENT=phpredis composer test
composer audit
```

Tests require PHP 8.1+ subject to framework requirements, SQLite PDO and an isolated Redis service. Without the port variable Redis tests skip explicitly. Preserve existing work, add a regression test for behavior changes, and describe compatibility and consistency implications. Update affected English and Arabic documentation alongside behavior changes. Package CI belongs in the package repository.

Compatibility lanes use Testbench 8/9/10/11 for Laravel 10/11/12/13. Legacy framework advisories must remain visible; allowing them in a disposable compatibility job is not a security endorsement or a consumer Composer policy change. Add tests for context propagation, ownership expiry and durable invalidation when changing those paths. TLS tests use short-lived local fixtures from tests/Support/tls-fixture.sh, never production credentials.
