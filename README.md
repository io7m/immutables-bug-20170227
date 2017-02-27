```
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.5.1:compile (default-compile) on project immutables-20170227: Compilation failure: Compilation failure:
[ERROR] /home/someone/git/com.github/io7m/immutables-bug-20170227/target/generated-sources/annotations/com/io7m/jregions/core/parameterized/ImmutablePAreaL.java:[213,21] <identifier> expected
[ERROR] /home/someone/git/com.github/io7m/immutables-bug-20170227/target/generated-sources/annotations/com/io7m/jregions/core/parameterized/ImmutablePAreaL.java:[223,16] invalid method declaration; return type required
```

```
  private <any> size;

  /**
   * {@inheritDoc}
   * <p>
   * Returns a lazily initialized value of the {@link PAreaL#size() size} attribute.
   * Initialized once and only once and stored for subsequent access with proper synchronization.
   * @return A lazily initialized value of the {@code l.name} attribute
   */
  @Override
  public <any> size() {
    if ((lazyInitBitmap & SIZE_LAZY_INIT_BIT) == 0) {
      synchronized (this) {
        if ((lazyInitBitmap & SIZE_LAZY_INIT_BIT) == 0) {
          this.size = Objects.requireNonNull(PAreaL.super.size(), "size");
          lazyInitBitmap |= SIZE_LAZY_INIT_BIT;
        }
      }
    }
    return size;
  }
```
