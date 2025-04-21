### Hi there 👋
[![trophy](https://github-profile-trophy.vercel.app/?username=hiro-oh)](https://github.com/ryo-ma/github-profile-trophy)

### My favorite Markdown referencing style
```md
## References
<!-- Inline links -->
- [Ref1: ]()
- [Ref2: ]()
- [Ref3: ]()

<!-- Reference-style links -->
[Ref1]:  ""
[Ref2]:  ""
[Ref3]:  ""
```

### My favorite PS prompt function
```ps1
function prompt {
    $path = (Get-Location).Path
    $gitBranch = ""

    # Gitリポジトリならブランチ名を取得
    if (git rev-parse --is-inside-work-tree 2>$null) {
        $branchName = git branch --show-current 2>$null
        if ($branchName) {
            $gitBranch = " (" + $branchName + ")"
        }
    }

    # パスの最後のディレクトリだけ色を変える
    $pathParts = $path -split '\\'  # Windowsのパス用
    if ($pathParts.Count -gt 1) {
        $basePath = ($pathParts[0..($pathParts.Count - 2)] -join "\") + "\"
        $currentDir = $pathParts[-1]
    } else {
        $basePath = ""
        $currentDir = $path
    }

    # プロンプトの表示（色付き）
    Write-Host "PS " -NoNewline -ForegroundColor Green
    Write-Host $basePath -NoNewline -ForegroundColor Blue  # 途中のパスは青
    Write-Host $currentDir -ForegroundColor Yellow  # 最後のディレクトリだけ黄色
    # ブランチ情報を改行して表示
    if ($gitBranch -ne "") {
        Write-Host $gitBranch -NoNewline -ForegroundColor Magenta # Gitブランチ名はマゼンタ
    }
    Write-Host "> " -NoNewline -ForegroundColor Cyan  # 入力プロンプトはシアン

    return " "
}
```



<!--
**hiro-oh/hiro-oh** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
