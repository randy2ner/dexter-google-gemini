# Skill Exchange

This directory is a shared handoff area for intentionally promoted importable `.skill` files. Project-specific packages belong directly in `projects/<project>/skill-exchange/`, with editable source in that project's `skills/` directory.

The guidance below can be copied and adapted for a project-local exchange. Keep the exchange flat; lifecycle subdirectories are not required. Store only importable package copies in an exchange and never treat it as editable Skill source.

## Handoff checklist

Before adding a package:

- Give it an unambiguous skill name and version.
- Preserve the package layout expected by Cowork.
- Confirm it contains no credentials or sensitive production data.
- Identify at least one linked case in the owning project's `test-plans/` directory.
- Do not overwrite a previously tested version.

Share the package alongside the governing Specifications and reusable Test Plans; those documents remain outside the runtime package unless the Skill host requires them. Record the exact filename tested and the dated observation in the relevant Test Plan. If import fails, record that outcome there rather than modifying the package in place.
