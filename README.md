# mysql_sys.x-io_global_by_file_by_latency-

SELECT 
    `performance_schema`.`file_summary_by_instance`.`FILE_NAME` AS `file`,
    `performance_schema`.`file_summary_by_instance`.`COUNT_STAR` AS `total`,
    `performance_schema`.`file_summary_by_instance`.`SUM_TIMER_WAIT` AS `total_latency`,
    `performance_schema`.`file_summary_by_instance`.`COUNT_READ` AS `count_read`,
    `performance_schema`.`file_summary_by_instance`.`SUM_TIMER_READ` AS `read_latency`,
    `performance_schema`.`file_summary_by_instance`.`COUNT_WRITE` AS `count_write`,
    `performance_schema`.`file_summary_by_instance`.`SUM_TIMER_WRITE` AS `write_latency`,
    `performance_schema`.`file_summary_by_instance`.`COUNT_MISC` AS `count_misc`,
    `performance_schema`.`file_summary_by_instance`.`SUM_TIMER_MISC` AS `misc_latency`
FROM
    `performance_schema`.`file_summary_by_instance`
ORDER BY `performance_schema`.`file_summary_by_instance`.`SUM_TIMER_WAIT` DESC
