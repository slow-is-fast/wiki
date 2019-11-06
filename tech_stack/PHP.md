# PHP

## Carbon
    计算两个日期相差几天
    两种方式，两种结果
    - 精确到天
    ```php
        Carbon::today()->diffInDays(Carbon::parse($user->created_at)->format('Y-m-d')) + 1
    ```

    
    - 精确到时分秒
    ```php
        Carbon::now()->diffInDays($user->created_at) + 1
    ```


## Validate Image

    ```php
    public function isValidImage($path)
    {
        if (file_exists($path) and exif_imagetype($path)) {
            return true;
        }
        return false;
    }
    ```
