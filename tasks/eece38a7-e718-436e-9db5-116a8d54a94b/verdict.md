# 裁决记录

- taskId:eece38a7-e718-436e-9db5-116a8d54a94b
- defectId:aecfa376-8966-4109-a119-f532192d1927
- runId:eece38a7-e718-436e-9db5-116a8d54a94b
- type:adopt_with_edits
- comment:S9 验收演示:按 owner 表修正后采纳

## 修正差异
- suspectedRootCause: "SettingsList refresh timeout at frame=42 cost=186ms, resulting in Choreographer skipped frames in TopLevelSettings homepage during fast scrolling." -> "SettingsList 刷新状态未收敛,快速滑动时触发 refresh timeout 并阻塞主线程。"
- duplicate: {"isDuplicate":true,"ofDefectRef":"HIST-SET-001","reason":"Both setting homepage and settings list jank are caused by SettingsList refresh timeout during rapid scrolling."} -> {"isDuplicate":true,"ofDefectRef":"HIST-SET-001","reason":"与历史设置首页滑动卡顿重复"}
- evidenceRefs: [{"kind":"code_path","ref":"packages/apps/Settings/src/com/android/settings/homepage/TopLevelSettings.kt","note":"Primary file path mapped to settings home jank flow and HIST-SET-001."},{"kind":"similar_defect","ref":"HIST-SET-001","note":"Historical defect for settings homepage scroll jank with refresh timeout."},{"kind":"log_line","ref":"SettingsList refresh timeout at frame=42 cost=186ms","note":"Direct log match with HIST-SET-001 and duplicate pairs pattern."}] -> [{"kind":"code_path","ref":"packages/apps/Settings/src/com/android/settings/homepage/TopLevelSettings.kt","note":"命中 Android Settings 顶层列表路径"},{"kind":"similar_defect","ref":"HIST-SET-001","note":"历史重复缺陷"},{"kind":"log_line","ref":"SettingsList refresh timeout","note":"issue 正文日志"}]
