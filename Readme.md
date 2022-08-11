# Usage
```golang
    srv := echo.New()
    fp, err := os.OpenFile("/var/log/echo/access.log", os.O_RDWR|os.O_CREATE|os.O_APPEND, 0666)
	if err != nil {
		panic(err)
	}

	logger := echo_alp_logger.LoggerWithConfig(echo_alp_logger.LoggerConfig{
		Output: fp,
	})

	srv.Use(logger)
```