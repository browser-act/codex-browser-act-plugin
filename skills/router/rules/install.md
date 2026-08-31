# Reviewed installation

The public plugin is reviewed only with `browser-act-cli==1.2.0.1` on Python 3.12.

1. Check the installed CLI with `browser-act --version`.
2. If the reported version is exactly `1.2.0.1`, continue.
3. If it is missing or different, explain that installation or replacement downloads an external package and that other versions have not been reviewed.
4. Only after explicit confirmation, install the pinned version:

   ```powershell
   uv tool install browser-act-cli==1.2.0.1 --python 3.12 --force
   ```

5. Re-run `browser-act --version` and stop unless the exact reviewed version is reported.

Do not upgrade automatically. A version change requires a fresh command/safety audit and a new plugin release.
