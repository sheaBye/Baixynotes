
flowable命名规则：

ACT_RE_* ：’ RE ’表示repository（存储）。RepositoryService接口操作的表。带此前缀的表包含的是静态信息，如，流程定义，流程的资源（图片，规则等）。
ACT_RU_* ：’ RU ’表示runtime。这是运行时的表存储着流程变量，用户任务，变量，职责（job）等运行时的数据。flowable只存储实例执行期间的运行时数据，当流程实例结束时，将删除这些记录。这就保证了这些运行时的表小且快。
ACT_ID_* : ’ ID ’表示identity(组织机构)。这些表包含标识的信息，如用户，用户组，等等。
ACT_HI_* : ’ HI ’表示history。就是这些表包含着历史的相关数据，如结束的流程实例，变量，任务，等等。
ACT_GE_* : 普通数据，各种情况都使用的数据。


4张表说明：

表分类	表名	表说明
一般数据(2)	ACT_GE_BYTEARRAY	通用的流程定义和流程资源
ACT_GE_PROPERTY	系统相关属性
流程历史记录(8)	ACT_HI_ACTINST	历史的流程实例
ACT_HI_ATTACHMENT	历史的流程附件
ACT_HI_COMMENT	历史的说明性信息
ACT_HI_DETAIL	历史的流程运行中的细节信息
ACT_HI_IDENTITYLINK	历史的流程运行过程中用户关系
ACT_HI_PROCINST	历史的流程实例
ACT_HI_TASKINST	历史的任务实例
ACT_HI_VARINST	历史的流程运行中的变量信息
用户用户组表(9)	ACT_ID_BYTEARRAY	二进制数据表
ACT_ID_GROUP	用户组信息表
ACT_ID_INFO	用户信息详情表
ACT_ID_MEMBERSHIP	人与组关系表
ACT_ID_PRIV	权限表
ACT_ID_PRIV_MAPPING	用户或组权限关系表
ACT_ID_PROPERTY	属性表
ACT_ID_TOKEN	系统登录日志表
ACT_ID_USER	用户表
流程定义表(3)	ACT_RE_DEPLOYMENT	部署单元信息
ACT_RE_MODEL	模型信息
ACT_RE_PROCDEF	已部署的流程定义
运行实例表(10)	ACT_RU_DEADLETTER_JOB	正在运行的任务表
ACT_RU_EVENT_SUBSCR	运行时事件
ACT_RU_EXECUTION	运行时流程执行实例
ACT_RU_HISTORY_JOB	历史作业表
ACT_RU_IDENTITYLINK	运行时用户关系信息
ACT_RU_JOB	运行时作业表
ACT_RU_SUSPENDED_JOB	暂停作业表
ACT_RU_TASK	运行时任务表
ACT_RU_TIMER_JOB	定时作业表
ACT_RU_VARIABLE	运行时变量表
其他表(2)	ACT_EVT_LOG	事件日志表
ACT_PROCDEF_INFO	流程定义信息