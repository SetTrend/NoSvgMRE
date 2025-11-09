# MAUI Fails To Convert Valid SVG Files Into PNG Files (Object reference not set to an instance of an object)

This repository serves as a minimum reproducible example providing steps to reproduce a [MAUI issue](https://github.com/dotnet/maui/issues/32460) which prevents valid SVG files from being converted into PNG files.

## Steps To Reproduce

1. Clone this repository to your local folder
1. Rebuild the solution

## Result

```
PS D:\Documents\Repos\NoSvgMRE> dotnet build --no-incremental
Rebuild finished (2,4s)
  NoSvgMRE net9.0-ios fails with 1 error(s) (1,9s)
    C:\Users\me\.nuget\packages\microsoft.maui.resizetizer\9.0.120\buildTransitive\Microsoft.Maui.Resizetizer.After.targets(449,9): error MAUI0000:
      System.NullReferenceException: Object reference not set to an instance of an object.
         at Microsoft.Maui.Resizetizer.SkiaSharpSvgTools.DrawUnscaled(SKCanvas canvas, Single scale) in /_/src/SinglePro      ject/Resizetizer/src/SkiaSharpSvgTools.cs:line 51
         at Microsoft.Maui.Resizetizer.SkiaSharpTools.Draw(SKBitmap tempBitmap, Double additionalScale, SKSize originalS      ize, Single scale, SKSizeI scaledSize) in /_/src/SingleProject/Resizetizer/src/SkiaSharpTools.cs:line 201
         at Microsoft.Maui.Resizetizer.SkiaSharpTools.Resize(DpiPath dpi, String destination, Double additionalScale, Bo      olean dpiSizeIsAbsolute) in /_/src/SingleProject/Resizetizer/src/SkiaSharpTools.cs:line 126
         at Microsoft.Maui.Resizetizer.Resizer.Rasterize(DpiPath dpi, String destination) in /_/src/SingleProject/Resize      tizer/src/Resizer.cs:line 114
         at Microsoft.Maui.Resizetizer.Resizer.Resize(DpiPath dpi, String inputsFile) in /_/src/SingleProject/Resizetize      r/src/Resizer.cs:line 105
         at Microsoft.Maui.Resizetizer.GenerateSplashStoryboard.WriteImages(Resizer resizer) in /_/src/SingleProject/Res      izetizer/src/GenerateSplashStoryboard.cs:line 63
         at Microsoft.Maui.Resizetizer.GenerateSplashStoryboard.Execute() in /_/src/SingleProject/Resizetizer/src/Genera      teSplashStoryboard.cs:line 43
  NoSvgMRE net9.0-android fails with 1 error(s) (2,8s)
    C:\Users\me\.nuget\packages\microsoft.maui.resizetizer\9.0.120\buildTransitive\Microsoft.Maui.Resizetizer.After.targets(423,9): error MAUI0000:
      System.NullReferenceException: Object reference not set to an instance of an object.
         at Microsoft.Maui.Resizetizer.SkiaSharpSvgTools.DrawUnscaled(SKCanvas canvas, Single scale) in /_/src/SinglePro      ject/Resizetizer/src/SkiaSharpSvgTools.cs:line 51
         at Microsoft.Maui.Resizetizer.SkiaSharpTools.Draw(SKBitmap tempBitmap, Double additionalScale, SKSize originalS      ize, Single scale, SKSizeI scaledSize) in /_/src/SingleProject/Resizetizer/src/SkiaSharpTools.cs:line 201
         at Microsoft.Maui.Resizetizer.SkiaSharpTools.Resize(DpiPath dpi, String destination, Double additionalScale, Bo      olean dpiSizeIsAbsolute) in /_/src/SingleProject/Resizetizer/src/SkiaSharpTools.cs:line 126
         at Microsoft.Maui.Resizetizer.Resizer.Rasterize(DpiPath dpi, String destination) in /_/src/SingleProject/Resize      tizer/src/Resizer.cs:line 114
         at Microsoft.Maui.Resizetizer.Resizer.Resize(DpiPath dpi, String inputsFile) in /_/src/SingleProject/Resizetize      r/src/Resizer.cs:line 105
         at Microsoft.Maui.Resizetizer.GenerateSplashAndroidResources.WriteImages(Resizer resizer) in /_/src/SingleProje      ct/Resizetizer/src/GenerateSplashAndroidResources.cs:line 72
         at Microsoft.Maui.Resizetizer.GenerateSplashAndroidResources.Execute() in /_/src/SingleProject/Resizetizer/src/      GenerateSplashAndroidResources.cs:line 46
  NoSvgMRE net9.0-maccatalyst successful (4,8s) → bin\Debug\net9.0-maccatalyst\maccatalyst-x64\NoSvgMRE.dll
  NoSvgMRE net9.0-windows10.0.19041.0 successful (25,0s) → bin\Debug\net9.0-windows10.0.19041.0\win10-x64\NoSvgMRE.dll

Failed to build with error(s) in 30,2s
PS D:\Documents\Repos\~Test\Maui\NoSvgMRE>
```