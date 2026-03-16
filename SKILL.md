---
name: skill-tester
description: OpenClaw Skill 全流程自动化测试工具，从下载、安装、配置到功能测试一键完成，生成完整测试报告
version: 1.0.0
author: HansXu-1986
license: MIT
---

# 🧪 skill-tester - OpenClaw Skill 全流程自动化测试

全自动测试已发布到 GitHub 的 OpenClaw Skill，覆盖下载、安装、配置、功能测试全流程，生成完整的测试报告，帮助开发者验证技能可用性。

## ✨ 特性

- 🚀 **一键全流程测试** - 从 git 克隆 → npx 安装 → 配置检查 → 功能测试，全自动完成
- 📊 **生成完整测试报告** - 每个步骤是否成功，错误信息一目了然
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

## Instructions

### 🧪 Testing Flow

1. **Collect test information**:
   - GitHub repository: `username/repo-name`
   - Skill name: (usually same as repo-name)
   - (Optional) Test configuration parameters

2. **Automated test steps**:
   1. Create temporary test directory
   2. Clone repository from GitHub
   3. Run `npx skills install` to install the skill locally
   4. Check if installation succeeds
   5. Verify SKILL.md exists and has correct format
   6. Check if all required files are present
   7. If configuration template provided, verify config format
   8. Try to load the skill and test basic function call
   9. Generate markdown test report with results for each step

3. **Output result**:
   - Show green checkmark for passed steps
   - Show red X for failed steps with error message
   - Give overall pass/fail verdict
   - Suggest fixes for any failed steps

4. **Cleanup**:
   - Remove temporary test directory (optional)

### 📋 Test Report Example

```markdown
# 🧪 Test Report: suno-api-music

## Test Result: ✅ PASSED

| Step | Result | Notes |
|------|--------|-------|
| 1. Clone from GitHub | ✅ Passed | Cloned successfully |
| 2. npx skills install | ✅ Passed | Installed to OpenClaw |
| 3. SKILL.md exists | ✅ Passed | Frontmatter format correct |
| 4. All required files | ✅ Passed | SKILL.md config.json example OK |
| 5. Skill loaded | ✅ Passed | Can be activated |
| 6. Basic function test | ✅ Passed | API connect OK |

## Overall
- **Status**: All tests passed! Skill is ready for publication.
- **Recommendation**: Ready to publish to SkillHub.
```

### ⚠️ Error Handling

- Clone failed → Check if repository exists and is public
- Install failed → Check SKILL.md format and repository structure
- SKILL.md missing → Remind developer that SKILL.md is required
- Function test failed → Give detailed error message for debugging

## Configuration

No configuration needed, all test parameters provided interactively.

## Pricing

- 🎉 **完全免费** - 开源工具，帮助开发者更好地测试技能
- 如果对你有帮助，欢迎赞赏支持开发 👇

![支付宝赞赏码](https://pcsdata.baidu.com/thumbnail/0105b65d3hc459885de5ae19b517cfa7?fid=843748537-16051585-645516420529129&rt=pr&sign=FDTAER-yUdy3dSFZ0SVxtzShv1zcMqd-2sh4WyLvEGJkEXw3S2lFgGSAX8M%3D&expires=2h&chkv=0&chkbd=0&chkpc=&dp-logid=575398625919898124&dp-callid=0&time=1773633600&bus_no=26&size=c1600_u1600&quality=100&vuk=-&ft=video)

## Changelog

### 1.0.0 (2026-03-16)
- Initial release
- Full流程自动化测试
- Generate markdown test report
- Cover all nodes from download to function test
