## 必装扩展（微软官方）
- Unity（VS Code 扩展）：提供 Unity 调试、Unity 专用分析器与代码修复、Unity 文件高亮
- C# Dev Kit：增强 C# 编辑体验（解决方案视图、测试、AI 辅助补全等）

说明：安装 Unity 扩展会自动拉取其依赖（包含 C# Dev Kit 与 C# 扩展），无需单独逐个安装。

## 推荐扩展（提升效率）
- YAML 支持：便于查看/编辑 `.yml` 配置（如部分包配置文件）
- Shader 语法支持：为 `.shader`/`.compute`/HLSL/ShaderLab 提供高亮与基础提示（在市场中搜索“ShaderLab”或“HLSL”）
- Git 工具（如 GitLens）：增强提交对比与历史查看
- EditorConfig：统一代码风格

## 在 Unity 中的必要配置
- 更新 VS Editor 包：`Window > Package Manager`，将 `Visual Studio Editor` 包升级到 `2.0.20` 或更高版本；不要使用已弃用的 `Visual Studio Code Editor` 包
- 设置外部脚本编辑器：`Edit > Preferences > External Tools`，将 `External Script Editor` 指向当前 IDE（VS Code/Trae IDE）
- 生成项目文件：在 `External Tools` 中启用生成 `.csproj/.sln`（若有选项），并点击 `Regenerate project files`

## 在 IDE 中的配置与调试
- 打开项目：在 IDE 中打开 Unity 项目根目录（包含 `Assets/`、`Packages/` 的文件夹）
- 首次加载：等待扩展索引解决方案；若提示安装依赖（.NET Runtime/Install Tool），按扩展向导完成
- 调试 Unity 编辑器：在 Unity 打开项目并运行后，IDE 中按 `F5` 或使用“Attach Unity Debugger”选择当前 `Unity Editor` 进程，即可断点调试
- 断点与热重载：在 C# 脚本设置断点；部分场景可使用扩展提供的热重载/快速附加能力

## 验证步骤（建议一次性完成）
- 在 Unity 中新建/打开脚本，确认会自动在 IDE 中打开且有 IntelliSense
- 在 `Update()` 或事件方法中下断点，`Play` 模式下命中断点
- 修改脚本保存后，回到 Unity `Compile` 成功且运行逻辑符合预期

## 常见问题排查
- 扩展未激活：确保已安装 Unity 扩展（会自动安装 C# Dev Kit 与 C# 扩展），并按向导完成依赖
- .sln/.csproj 缺失：在 Unity `Preferences > External Tools` 勾选生成项目文件并重新生成
- 无法附加调试器：确认 Unity 版本 ≥ 2021，IDE 中选择“Attach Unity Debugger”的正确进程；若仍异常，重启 Unity 与 IDE

## 参考资料
- Unity 与 VS Code 官方整合指南：https://code.visualstudio.com/docs/other/unity
- Unity 扩展发布介绍（微软）：https://devblogs.microsoft.com/visualstudio/announcing-the-unity-extension-for-visual-studio-code/
- Unity 扩展 GA 公告（微软 .NET 博客）：https://devblogs.microsoft.com/dotnet/unity-extension-for-visual-studio-code-now-generally-available/
- Unity 官方调试教程（VS Code）：https://unity.com/how-to/debugging-with-microsoft-visual-studio-code