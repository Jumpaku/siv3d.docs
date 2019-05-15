
```C++
# include <Siv3D.hpp>

void Main()
{
	Scene::SetBackground(ColorF(0.8, 0.9, 1.0));

	const Font font(60);

	const Texture cat(Emoji(U"🐈"));

	Vec2 catPos(650, 450);

	while (System::Update())
	{
		font(U"Hello, Siv3D!🐣").drawAt(Scene::Center(), Palette::Black);

		font(Cursor::Pos()).draw(20, 500, ColorF(0.6));

		cat.resized(80).drawAt(catPos);

		Circle(Cursor::Pos(), 40).draw(ColorF(1, 0, 0, 0.5));

		if (KeyA.down())
		{
			Print << U"Hello!";
		}

		if (SimpleGUI::Button(U"Move the cat", Vec2(600, 20)))
		{
			catPos = RandomVec2(Scene::Rect());
		}
	}
}
```

# Siv3D をはじめよう
## 必要な環境
### Windows
- Windows 7 SP1 / 8.1 / 10 (64-bit)
- **Visual Studio 2019 version 16.0**
    - Visual Studio Installer で **C++ によるデスクトップ開発** をインストールしてください

### macOS
- macOS High Sierra v10.13 以降
- Xcode 10.1 以降

## OpenSiv3D SDK のインストール
### Windows
1. **[OpenSiv3D Installer for Windows Desktop](#)** をダウンロードして実行します。

!!! note
    OpenSiv3D SDK を削除するには、コントロールパネルからアンインストールします。

### macOS
1. **[OpenSiv3D Project Templates for macOS](#)** をダウンロードしてファイルを展開します。


## OpenSiv3D アプリのビルド
### Windows
1. Visual Studio 2019 のスタート画面で **新しいプロジェクトの作成** をクリックし、**新しいプロジェクトの作成** ダイアログに進みます。
2. プロジェクトテンプレート一覧の中から **OpenSiv3D(インストールしたバージョン)** を選択し、**次へ** を押します。
3. プロジェクト名を入力します。
4. 入力した設定でプロジェクトを作成するために、**作成** を押します。
5. **ビルド** メニューからプロジェクトをビルドします。
6. **デバッグ** メニューの **デバッグの開始** でビルドしたプログラムを実行します。

### macOS
1. プロジェクトファイル (siv3d_vX.X.X_macOS/examples/empty/empty.xcodeproj) を Xcode で開きます。
2. **実行ボタン ▶️** を押すと、プログラムをビルドして実行します。
