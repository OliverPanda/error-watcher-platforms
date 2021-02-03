### sentry初始化
```
// main.js
import * as Sentry from '@sentry/vue'
import { Integrations } from '@sentry/tracing'
Sentry.init({
  Vue: Vue,
  // dsn: sentry的唯一key, Settings > Client Keys里获取
  dsn: 'https://bb14b6706f034bc696c03866180c51fe@o514903.ingest.sentry.io/5618867',
  integrations: [new Integrations.BrowserTracing()],
  tracesSampleRate: 1.0
})
```

### sourcemap上传
```
// vue.config.js
const SentryWebpackPlugin = require('@sentry/webpack-plugin')
module.exports = {
  // ...other code
  configureWebpack: {
    plugins: [
      new SentryWebpackPlugin({
        // sentry-cli configuration
        authToken: process.env.SENTRY_AUTH_TOKEN,
        org: 'exmaple-org',
        project: process.env.VUE_APP_CONTEXT, // 项目名
        // webpack specific configuration
        include: '.',
        ignore: ['node_modules', 'webpack.config.js']
      })
    ]
  },
  // ...other code
}
```