# WebStorm + Writerside — IEDIAdminDoc

## Help module path

Register:

```text
Writerside/
```

(the directory containing `writerside.cfg`).

## IDE setup

1. Install the **Writerside** plugin and restart WebStorm.
2. Open the **IEDIAdminDoc** repository.
3. **View → Tool Windows → Writerside** → **Add documentation** → **To current project** → select `Writerside`.
4. Instance **iEDI Admin Guide** → **Build → Web Archive**.

## Content

- Edit `Writerside/topics/*.md` only.
- TOC: `Writerside/iedi-adm.tree`
- Branding: `Writerside/cfg/buildprofiles.xml`

## Docker (CI parity)

```bash
docker run --rm -v "$(pwd)":/data jetbrains/writerside-builder:243.22562 \
  --instance Writerside/iedi-adm
```

Publish: push to GitHub; see [GITHUB_PAGES_SETUP.md](./GITHUB_PAGES_SETUP.md).
