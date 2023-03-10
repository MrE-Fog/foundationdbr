.. _developer-guide-error-codes:

Error Codes
===========

FoundationDB may return the following error codes from API functions. If you need to check for specific errors (for example, to implement custom retry logic), you must use the numerical code, since the other fields are particularly likely to change unexpectedly. Error handling logic should also be prepared for new error codes which are not listed here.

+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| Name                                          | Code| Description                                                                    |
+===============================================+=====+================================================================================+
| success                                       |    0| Success                                                                        |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| operation_failed                              | 1000| Operation failed                                                               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| timed_out                                     | 1004| Operation timed out                                                            |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| transaction_too_old                           | 1007| Transaction is too old to perform reads or be committed                        |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| future_version                                | 1009| Request for future version                                                     |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| not_committed                                 | 1020| Transaction not committed due to conflict with another transaction             |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| commit_unknown_result                         | 1021| Transaction may or may not have committed                                      |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| transaction_cancelled                         | 1025| Operation aborted because the transaction was cancelled                        |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| transaction_timed_out                         | 1031| Operation aborted because the transaction timed out                            |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| too_many_watches                              | 1032| Too many watches currently set                                                 |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| watches_disabled                              | 1034| Watches cannot be set if read your writes is disabled                          |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| accessed_unreadable                           | 1036| Read or wrote an unreadable key                                                |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| process_behind                                | 1037| Storage process does not have recent mutations                                 |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| database_locked                               | 1038| Database is locked                                                             |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| cluster_version_changed                       | 1039| Cluster has been upgraded to a new protocol version                            |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| external_client_already_loaded                | 1040| External client has already been loaded                                        |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| proxy_memory_limit_exceeded                   | 1042| CommitProxy commit memory limit exceeded                                       |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| batch_transaction_throttled                   | 1051| Batch GRV request rate limit exceeded                                          |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| operation_cancelled                           | 1101| Asynchronous operation cancelled                                               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| future_released                               | 1102| Future has been released                                                       |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| tag_throttled                                 | 1213| Transaction tag is being throttled                                             |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| platform_error                                | 1500| Platform error                                                                 |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| large_alloc_failed                            | 1501| Large block allocation failed                                                  |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| performance_counter_error                     | 1502| QueryPerformanceCounter error                                                  |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| io_error                                      | 1510| Disk i/o operation failed                                                      |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| file_not_found                                | 1511| File not found                                                                 |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| bind_failed                                   | 1512| Unable to bind to network                                                      |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| file_not_readable                             | 1513| File could not be read                                                         |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| file_not_writable                             | 1514| File could not be written                                                      |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| no_cluster_file_found                         | 1515| No cluster file found in current directory or default location                 |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| file_too_large                                | 1516| File too large to be read                                                      |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| client_invalid_operation                      | 2000| Invalid API call                                                               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| commit_read_incomplete                        | 2002| Commit with incomplete read                                                    |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| test_specification_invalid                    | 2003| Invalid test specification                                                     |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| key_outside_legal_range                       | 2004| Key outside legal range                                                        |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| inverted_range                                | 2005| Range begin key larger than end key                                            |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| invalid_option_value                          | 2006| Option set with an invalid value                                               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| invalid_option                                | 2007| Option not valid in this context                                               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| network_not_setup                             | 2008| Action not possible before the network is configured                           |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| network_already_setup                         | 2009| Network can be configured only once                                            |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| read_version_already_set                      | 2010| Transaction already has a read version set                                     |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| version_invalid                               | 2011| Version not valid                                                              |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| range_limits_invalid                          | 2012| Range limits not valid                                                         |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| invalid_database_name                         | 2013| Database name must be 'DB'                                                     |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| attribute_not_found                           | 2014| Attribute not found in string                                                  |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| future_not_set                                | 2015| Future not ready                                                               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| future_not_error                              | 2016| Future not an error                                                            |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| used_during_commit                            | 2017| Operation issued while a commit was outstanding                                |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| invalid_mutation_type                         | 2018| Unrecognized atomic mutation type                                              |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| transaction_invalid_version                   | 2020| Transaction does not have a valid commit version                               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| no_commit_version                             | 2021| Transaction is read-only and therefore does not have a commit version          |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| environment_variable_network_option_failed    | 2022| Environment variable network option could not be set                           |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| transaction_read_only                         | 2023| Attempted to commit a transaction specified as read-only                       |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| invalid_cache_eviction_policy                 | 2024| Invalid cache eviction policy, only random and lru are supported               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| network_cannot_be_restarted                   | 2025| Network can only be started once                                               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| blocked_from_network_thread                   | 2026| Detected a deadlock in a callback called from the network thread               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| incompatible_protocol_version                 | 2100| Incompatible protocol version                                                  |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| transaction_too_large                         | 2101| Transaction exceeds byte limit                                                 |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| key_too_large                                 | 2102| Key length exceeds limit                                                       |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| value_too_large                               | 2103| Value length exceeds limit                                                     |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| connection_string_invalid                     | 2104| Connection string invalid                                                      |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| address_in_use                                | 2105| Local address in use                                                           |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| invalid_local_address                         | 2106| Invalid local address                                                          |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| tls_error                                     | 2107| TLS error                                                                      |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| unsupported_operation                         | 2108| Operation is not supported                                                     |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| too_many_tags                                 | 2109| Too many tags set on transaction                                               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| tag_too_long                                  | 2110| Tag set on transaction is too long                                             |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| too_many_tag_throttles                        | 2111| Too many tag throttles have been created                                       |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| special_keys_cross_module_read                | 2112| Special key space range read crosses modules.                                  |
|                                               |     | Refer to the ``SPECIAL_KEY_SPACE_RELAXED`` transaction option for more details.|
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| special_keys_no_module_found                  | 2113| Special key space range read does not intersect a module.                      |
|                                               |     | Refer to the ``SPECIAL_KEY_SPACE_RELAXED`` transaction option for more details.|
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| special_keys_write_disabled                   | 2114| Special key space is not allowed to write by default. Refer                    |
|                                               |     | to the ``SPECIAL_KEY_SPACE_ENABLE_WRITES`` transaction option for more details.|
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| special_keys_no_write_module_found            | 2115| Special key space key or keyrange in set or clear does not intersect a module. |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| special_keys_cross_module_write               | 2116| Special key space clear crosses modules                                        |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| special_keys_api_failure                      | 2117| Api call through special keys failed. For more information, read the           |
|                                               |     | ``0xff0xff/error_message`` key                                                 |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| tenant_name_required                          | 2130| Tenant name must be specified to access data in the cluster                    |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| tenant_not_found                              | 2131| Tenant does not exist                                                          |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| tenant_already_exists                         | 2132| A tenant with the given name already exists                                    |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| tenant_not_empty                              | 2133| Cannot delete a non-empty tenant                                               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| invalid_tenant_name                           | 2134| Tenant name cannot begin with \xff                                             |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| tenant_prefix_allocator_conflict              | 2135| The database already has keys stored at the prefix allocated for the tenant    |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| tenants_disabled                              | 2136| Tenants have been disabled in the cluster                                      |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| api_version_unset                             | 2200| API version is not set                                                         |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| api_version_already_set                       | 2201| API version may be set only once                                               |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| api_version_invalid                           | 2202| API version not valid                                                          |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| api_version_not_supported                     | 2203| API version not supported                                                      |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| exact_mode_without_limits                     | 2210| EXACT streaming mode requires limits, but none were given                      |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| unknown_error                                 | 4000| An unknown error occurred                                                      |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
| internal_error                                | 4100| An internal error occurred                                                     |
+-----------------------------------------------+-----+--------------------------------------------------------------------------------+
