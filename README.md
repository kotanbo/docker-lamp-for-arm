# ARM 系 CPU で動作する Apache, MariaDB, PHP の開発環境

- Apache/2.4.51 (Debian)
- PHP 7.4.27
- 10.7.1-MariaDB-1:10.7.1+maria~focal-log - mariadb.org binary distribution
  - user : root
  - password : password
- Xdebug 3.1.2
  - port : 9003

## Requirement

- Docker
- Docker Compose

## Usage

1. ドキュメントルートと同期される src ディレクトリにソース設置
2. 起動
    ```sh
    $ docker-compose up -d
    ```

## Reference

https://qiita.com/ucan-lab/items/56c9dc3cf2e6762672f4

## License

MIT