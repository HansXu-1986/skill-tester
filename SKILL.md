---
name: skill-tester
description: OpenClaw Skill 全流程自动化测试工具，从下载、安装、配置到功能测试一键完成，实时显示每一步结果，生成完整测试报告
version: 1.1.0
author: HansXu-1986
license: MIT
---

# 🧪 skill-tester - OpenClaw Skill 全流程自动化测试

全自动测试已发布到 GitHub 的 OpenClaw Skill，覆盖下载、安装、配置、功能测试全流程，**实时显示每一步测试结果**，生成完整的测试报告，帮助开发者验证技能可用性。

## ✨ 特性

- 🚀 **一键全流程测试** - 从 git 克隆 → npx 安装 → 配置检查 → 功能测试，全自动完成
- 👁️ **实时显示进度** - 每一步执行完立即显示结果，不等到最后
- 📊 **生成完整测试报告** - 每个步骤是否成功，错误信息一目了然，Markdown 格式
- 🔍 **覆盖所有节点** - 下载/安装/配置/功能，每个环节都测试
- 📝 **支持参数配置** - 可以指定测试哪个仓库，哪个技能
- ✅ **符合 SkillHub 规范** - 验证技能是否符合发布标准

## When to use

Use this skill when:

1. You have developed and published a new OpenClaw Skill to GitHub
2. You want to verify the whole process from download to usage works correctly
3. You need a test report before publishing to SkillHub
4. You want to test an existing published skill for regressions
5. Helps you find and fix installation/usage issues before users encounter them
6. You want to see each step's result in real-time

## Instructions

### 🧪 Testing Flow

1. **Collect test information**:
   - GitHub repository: `username/repo-name`
   - Skill name: (usually same as repo-name)
   - (Optional) Test configuration parameters

2. **Automated test steps** - *each step shows result immediately*:

   | Step | Action | What it checks |
   |------|--------|--------------|
   | 1️⃣ | Create temporary directory | Check workspace can be written |
   | 2️⃣ | Clone repository from GitHub | Check repo exists and is accessible |
   | 3️⃣ | Run `npx skills install` | Check installation process |
   | 4️⃣ | Check SKILL.md exists | Verify skill has description |
   | 5️⃣ | Validate SKILL.md frontmatter | Check name/description/version format |
   | 6️⃣ | Check required files | Verify all essential files present |
   | 7️⃣ | Verify config.json template (if any) | Check JSON format |
   | 8️⃣ | Install completed | Check skill installed to correct location |
   | 9️⃣ | (Optional) Basic function test | If test parameters provided, try basic call |

   > **Real-time output**: After each step completes, the result is displayed immediately (✅ Pass / ❌ Fail)

3. **Generate final test report**:
   - Markdown format table with all steps
   - Green checkmark for passed steps
   - Red X for failed steps with error message
   - Overall pass/fail verdict
   - Specific fix suggestions for any failures

4. **Output result**:
   - Show full report
   - Give conclusion whether skill is ready for publication
   - Cleanup temporary directory (optional)

### 📋 Test Report Example

```markdown
# 🧪 Test Report: github-skill-publish v1.1.0

## Test Result: ✅ ALL TESTS PASSED

| Step | Result | Notes |
|------|--------|-------|
| 1. Create temp directory | ✅ Passed | /tmp/test-github-skill-publish created |
| 2. Clone from GitHub | ✅ Passed | Cloned successfully from HansXu-1986/github-skill-publish |
| 3. npx skills install | ✅ Passed | Installed to OpenClaw successfully |
| 4. SKILL.md exists | ✅ Passed | SKILL.md found (3.5KB) |
| 5. Validate frontmatter | ✅ Passed | name/description/version all present |
| 6. Check required files | ✅ Passed | All essential files OK |
| 7. Verify config.json | ✅ Passed | JSON format correct |
| 8. Check installation | ✅ Passed | Symlink created correctly |

## Overall
- **Status**: All 8 tests passed!
- **Conclusion**: Skill is ready for publication to SkillHub.
- **Recommendation**: Good to go! 🎉
```

### ⚠️ Error Handling

- Clone failed → Check if repository exists and is public, verify PAT if needed
- Install failed → Check SKILL.md format and repository structure
- SKILL.md missing → Remind developer that SKILL.md is required
- Frontmatter invalid → Tell developer which field is missing
- Function test failed → Give detailed error message for debugging

## Configuration

No configuration needed, all test parameters provided interactively when testing.

## Pricing

- 🎉 **完全免费** - 开源工具，帮助开发者更好地测试技能
- 如果对你有帮助，欢迎赞赏支持开发 👇

![支付宝赞赏码](https://pcsdata.baidu.com/thumbnail/0105b65d3hc459885de5ae19b517cfa7?fid=843748537-16051585-645516420529129&rt=pr&sign=FDTAER-yUdy3dSFZ0SVxtzShv1zcMqd-2sh4WyLvEGJkEXw3S2lFgGSAX8M%3D&expires=2h&chkv=0&chkbd=0&chkpc=&dp-logid=575398625919898124&dp-callid=0&time=1773633600&bus_no=26&size=c1600_u1600&quality=100&vuk=-&ft=video)

## 💬 反馈与建议

如果你使用中遇到问题，或者有好的建议，欢迎反馈：

- 🐛 **问题报告**: [点击这里报告 Bug](https://github.com/HansXu-1986/skill-tester/issues/new)
- 💡 **功能建议**: [点击这里提建议](https://github.com/HansXu-1986/skill-tester/issues/new)

感谢你的反馈，帮助我们变得更好 🙏

## Changelog

### 1.1.0 (2026-03-16)
- ✨ **New**: Real-time display of each step's result immediately after execution
- ✨ **Improved**: More detailed checking (frontmatter validation, config.json format check)
- 📊 Better organized test report with clear pass/fail status
- 🎯 More specific fix suggestions for failed tests

### 1.0.0 (2026-03-16)
- Initial release
- Full流程自动化测试
- Generate markdown test report
- Cover all nodes from download to function test
