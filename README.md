# ZMK Keyboard Module: Dao

ZMK firmware support for the [Dao](https://github.com/yumagulovrn/dao-choc-ble) split ergonomic keyboard.

## Features

- Split keyboard (dao_left, dao_right)
- nRF52840-based wireless (BLE)
- USB support
- Battery voltage monitoring

## Usage

Add this module to your ZMK config's `west.yml`:

```yaml
manifest:
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: your-github
      url-base: https://github.com/your-username
  projects:
    - name: zmk
      remote: zmkfirmware
      revision: main
      import: app/west.yml
    - name: zmk-keyboard-dao
      remote: ozalexo
      revision: main
  self:
    path: config
```

Then add `dao_left` and `dao_right` to your `build.yaml`:

```yaml
include:
  - board: dao_left
  - board: dao_right
```

## License

MIT
