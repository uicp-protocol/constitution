# SUZIE V1 activation / การเปิดใช้งาน

The repository contains an executable GitHub Actions workflow and Python agent runtime. It is **not yet confirmed active** until credentials and repository workflow permissions are configured.

1. Repository **Settings → Secrets and variables → Actions → New repository secret**: set `OPENAI_API_KEY` (never commit the key).
2. Repository **Settings → Actions → General → Workflow permissions**: allow GitHub Actions to create pull requests, and grant read/write permissions as permitted by organization policy.
3. **Actions → SUZIE Agent — Research Digest → Run workflow** for first test.
4. Review the run logs and the resulting draft PR; merge only after human review.
5. A daily schedule (02:17 UTC) is included, but GitHub may delay or skip scheduled jobs.

The workflow reads up to 20 open issues, uses an OpenAI model to draft a research digest, and opens a **pull request**. It does not ratify the constitution, edit core pillars, or autonomously merge. The issue text is untrusted input. GitHub's workflow permissions and API billing must be monitored.

**Security note:** This is an initial reference implementation, not a hardened autonomous system. Production deployment needs stronger prompt-injection defenses, monitoring, rate limits, and scoped identity/memory.

ภาษาไทย: ต้องตั้งค่า Secret และสิทธิ์ GitHub Actions ก่อน จึงจะทำงานได้จริง ระบบสร้างร่างรายงานเป็น Pull Request เพื่อให้ตรวจสอบ ไม่อนุมัติธรรมนูญหรือ Merge เอง
