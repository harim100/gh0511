<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<title>복사 중...</title>
<style>
body {
  font-family: sans-serif;
  text-align: center;
  margin-top: 80px;
}
</style>
</head>
<body>
  <p>자동으로 복사 중입니다...</p>
  <script>
  const TEXT_TO_COPY = "✅ 이 텍스트가 자동으로 복사됩니다.";

  async function copyAndClose() {
    try {
      await navigator.clipboard.writeText(TEXT_TO_COPY);
      document.body.innerHTML = "<p>복사 완료! 창이 닫힙니다...</p>";
      setTimeout(() => window.close(), 800);
    } catch (e) {
      document.body.innerHTML = `
        <p>자동 복사 실패 ❌</p>
        <p>아래 텍스트를 직접 복사해주세요.</p>
        <textarea rows="3" cols="30">${TEXT_TO_COPY}</textarea>`;
    }
  }

  // 팝업은 부모 창에서 클릭으로 열렸으므로 user gesture로 인정되어 복사 가능
  copyAndClose();
  </script>
</body>
</html>
