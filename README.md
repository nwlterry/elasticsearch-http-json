# elasticsearch-http-json

Example Elastic Agent `httpjson` input that polls the DolphinScheduler REST API for running process instances.

## File

`dolphinscheduler_poller.yaml`

- Input type: `httpjson`
- Data stream namespace: `monitoring`
- Poll interval: 1 minute
- GET `.../dolphinscheduler/projects/{{project_code}}/process-instances`
- Splits `body.data.totalList` into events
- Cursor pagination via `process_id`

Replace `your-ds-host`, `{{project_code}}`, and `{{your_token}}` before using. Prefer Fleet secrets/vars for the token rather than a plaintext header.

Related dashboards: [dolphinscheduler-dashboards](https://github.com/nwlterry/dolphinscheduler-dashboards).
