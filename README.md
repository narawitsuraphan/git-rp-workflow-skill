# Git & RP Workflow

A reusable Codex skill for safer Git collaboration, roleplay story repositories, release planning, and recovery from common Git mistakes.

## Download

- [Download the complete skill as a ZIP](https://github.com/narawitsuraphan/git-rp-workflow-skill/archive/refs/heads/codex/publish-git-rp-workflow.zip)
- [Browse the skill and reference files](https://github.com/narawitsuraphan/git-rp-workflow-skill/tree/codex/publish-git-rp-workflow/skills/git-rp-workflow)
- [Open SKILL.md](https://raw.githubusercontent.com/narawitsuraphan/git-rp-workflow-skill/codex/publish-git-rp-workflow/skills/git-rp-workflow/SKILL.md)

Install the whole **git-rp-workflow** folder, including **references/**. The reference guides contain the detailed workflows.

## What it can do

- **Git and pull requests:** inspect repository state, plan branches and commits, write clear PR descriptions, review changes, and handle merge conflicts carefully.
- **Roleplay repositories:** organize a story bible with character sheets, world facts, scenes, session logs, canon notes, and alternate timelines.
- **Releases:** plan version numbers, changelogs, tags, and release checklists.
- **Recovery:** guide safer responses to common mistakes such as working on the wrong branch, accidental commits, or messy merges.

The skill provides reusable instructions to Codex; it is not a standalone application.

## Install in Codex

Download and extract the ZIP. From the extracted repository folder, copy the complete skill folder into your Codex skills directory.

PowerShell:

    $codexHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $HOME ".codex" }
    $skillsPath = Join-Path $codexHome "skills"
    New-Item -ItemType Directory -Force -Path $skillsPath | Out-Null
    Copy-Item -Recurse -Force ".\skills\git-rp-workflow" $skillsPath

macOS or Linux:

    if [ -n "$CODEX_HOME" ]; then
      CODEX_DIR="$CODEX_HOME"
    else
      CODEX_DIR="$HOME/.codex"
    fi
    mkdir -p "$CODEX_DIR/skills"
    cp -R skills/git-rp-workflow "$CODEX_DIR/skills/"

Restart Codex if the skill does not appear. You can invoke it with **$git-rp-workflow**, or Codex may select it automatically when a request matches.

## Files

- **skills/git-rp-workflow/SKILL.md** — the main skill instructions.
- **skills/git-rp-workflow/references/** — detailed guides for pull requests, roleplay repositories, releases, and Git recovery.

## License

The skill and its reference files are shared under [Creative Commons Attribution 4.0 International (CC BY 4.0)](./LICENSE). You may share and adapt them, including commercially. Credit **narawitsuraphan**, link to this repository and the license, and indicate whether you made changes.

## ภาษาไทย

Git & RP Workflow เป็น Codex skill สำหรับช่วยทำงานกับ Git จัดระเบียบ repository สำหรับ roleplay วางแผน release และรับมือกับข้อผิดพลาดทั่วไปของ Git

### ทำอะไรได้บ้าง

- **Git และ pull request:** ตรวจสถานะ repository วางแผน branch และ commit เขียนคำอธิบาย PR ให้ชัดเจน ตรวจการเปลี่ยนแปลง และจัดการ merge conflict อย่างระมัดระวัง
- **repository สำหรับ roleplay:** จัด story bible ให้แยกข้อมูลตัวละคร โลก ฉาก บันทึกแต่ละ session ข้อเท็จจริงที่เป็น canon และเส้นเรื่องทางเลือก
- **การ release:** วางแผนเลขเวอร์ชัน changelog tag และรายการตรวจสอบก่อน release
- **การกู้คืน:** แนะนำวิธีรับมืออย่างปลอดภัยเมื่ออยู่ผิด branch เผลอ commit หรือมี merge ที่ยุ่งยาก

### ดาวน์โหลดและติดตั้ง

- [ดาวน์โหลด skill ทั้งชุดเป็น ZIP](https://github.com/narawitsuraphan/git-rp-workflow-skill/archive/refs/heads/codex/publish-git-rp-workflow.zip)
- [ดูโฟลเดอร์ skill และไฟล์อ้างอิง](https://github.com/narawitsuraphan/git-rp-workflow-skill/tree/codex/publish-git-rp-workflow/skills/git-rp-workflow)

แตก ZIP แล้วคัดลอกโฟลเดอร์ **skills/git-rp-workflow** ทั้งโฟลเดอร์ รวมถึง **references** ไปไว้ที่ **CODEX_HOME/skills/** หากไม่ได้ตั้งค่า CODEX_HOME ตำแหน่งทั่วไปคือ %USERPROFILE%/.codex/skills บน Windows และ **~/.codex/skills/** บน macOS/Linux จากนั้นเริ่ม Codex ใหม่หากยังไม่เห็น skill เรียกใช้ด้วย **$git-rp-workflow** ได้ หรือ Codex อาจเลือกให้อัตโนมัติเมื่อคำขอตรงกับงานของ skill

### ใบอนุญาต

เผยแพร่ภายใต้ CC BY 4.0 สามารถแชร์และดัดแปลงได้ รวมถึงใช้เชิงพาณิชย์ โดยให้เครดิต **narawitsuraphan** ลิงก์ repository และใบอนุญาต พร้อมระบุการเปลี่ยนแปลง ดูรายละเอียดใน [LICENSE](./LICENSE)
