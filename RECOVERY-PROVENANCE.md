# 本目录来源说明（2026-11-04 恢复）

本目录由 DeepSeek Harness 会话在 2026-11-04 从两条证据链恢复：

1. GitHub 私有仓库 https://github.com/zhouyan19920115/DSHHarmony
   commit 08f074e2f5e90b1584bccc169aeb76aac8894c3a（2026-10-23 00:30 UTC）
   —— 原样文件（121 个），补齐了 cpp/资源/截图/配置等。
2. 本机 DSH 会话日志 %USERPROFILE%\.dsh\sessions\--D-APP-Deepseek-DSHHarmony--
   —— 回放 write/edit/read 结构化全文，重建 388 个文件（内容比仓库新，覆盖到 11-04）。
3. certificate/ 下 6 个签名文件：
   - DSHHarmony.csr / DSHHarmony.p12：从旧安装目录 D:\APP\Deepseek.old-{GUID}\DSHHarmony\certificate 抢救出的原始文件
   - DSHHarmony.cer / DSHHarmony-debug.cer / DSHRelease.p7b / DSHdebugDebug.p7b：
     从 %USERPROFILE%\Downloads\ 的原始下载件恢复（DSHdebug.cer 即原 DSHHarmony-debug.cer）
   已校验：p12 私钥（口令见工程文档/会话记录）与 release、debug 两张叶证书公钥一致；
   profile 的 bundle-info.bundle-name = com.dshhugozhou.cn，与 AppScope/app.json5 一致。
   ⚠️ p12 内含私钥，切勿提交到 git / 上传网盘。

## 已知缺失（无法从日志/仓库恢复）
- dist/*.exe 打包产物、harmony/entry/build、.hvigor、node_modules、oh_modules（可再生）
- docs/screenshots 约 90 张手机截图（二进制，git 里只有 15 张早期截图）
- tools/dsh-monitor 的少量文档/探测脚本
- bridge/src/state.js、bridge/src/core.js 经核实**从未存在**（当时排查日志里的“找不到该路径”就是证据），无需补写

## 恢复后建议
1. 在本目录执行一次构建验证：DevEco Studio 打开 harmony/，或 hvigorw assembleHap（build-profile 的签名配置指向 %USERPROFILE%\.ohos\config\<你的debug证书>，该文件仍在）。
2. 提交并推到远端：git remote add origin https://github.com/zhouyan19920115/DSHHarmony.git; git push。
3. 工程不要放回应用安装目录（D:\APP\Deepseek 内），避免升级再次被删。

生成时间：2026-11-04 23:15 (Asia/Shanghai)
