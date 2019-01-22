---
title: Project Server 错误代码
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
f1_keywords:
- error codes
- errors
- Project Server errors
- PSErrorID
- PSI errors
keywords:
- psi, 错误代码,错误代码, Project Server,PSErrorID,Project Server Interface, 错误代码,Project Server, 错误代码
ms.assetid: db78a09c-ebef-47cc-8623-40abe117aa08
description: 本主题包含 Project Server 2013 中 Project Server Interface (PSI) 的错误代码表。 表按功能区和错误代码范围排列。
localization_priority: Priority
ms.openlocfilehash: c61821bcb85fa3bd83601659850577eaa93eda61
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705594"
---
# <a name="project-server-error-codes"></a>Project Server 错误代码

本主题包含 Project Server 2013 中 Project Server Interface (PSI) 的错误代码表。 表按功能区和错误代码范围排列。
   
Project Server 2013 进程和 PSI 方法具有通常按功能区排列的错误代码编号。 [Microsoft.Office.Project.Server.Library.PSErrorID](https://msdn.microsoft.com/library/microsoft.office.project.server.library.pserrorid_di_pj14mref(v=office.14).aspx) 中的枚举在 [WebSvcProject.PSErrorID](https://msdn.microsoft.com/library/office/websvcproject.pserrorid_di_pj14mref.aspx) 中重复；它们按名称字母顺序列出错误代码。 本主题列出了表中按 PSI 类或功能区以及错误标识符 (ID) 编号排列的错误代码。 
  
> [!NOTE]
>  许多错误代码是通用的，并且可能有多种可能的原因。有关错误的详细信息，你可以执行以下操作： 
> - 对于基于 ASMX 的应用程序，可使用 **System.Web.Services.Protocols.SoapException** 与 **PSClientError** 对象显示 PSI 方法调用错误的列表或层次结构。请参阅 [ASMX 的错误代码示例](#pj15_ErrorCodes_ASMXExample)。 
> - 对于基于 WCF 的应用程序，可使用 **System.ServiceModel.FaultException** 获取 **PSClientError** 对象，还可获取其他错误信息。请参阅 [WCF 的错误代码示例](#pj15_ErrorCodes_WCFExample)。 
> - 使用 Project Server 计算机上的应用程序事件日志。
> - 使用统一日志记录服务 (ULS) 跟踪日志。 有关说明，请参阅 [Project 2010 开发入门](https://msdn.microsoft.com/library/gg607685.aspx)中的*检查错误*部分。 
> - 有关使用 ULS 日志的详细信息，请参阅 Project 支持博客文章 [Project Server 2010：出现意外情况时所需的操作](https://blogs.msdn.com/b/brismith/archive/2010/03/24/project-server-2010-what-to-expect-when-you-get-the-unexpected.aspx)，并可搜索“阅读 ULS 日志”博客。 
> - 为了有助于查找或查看 ULS 数据中的具体问题，请使用 [ULS 查看器](https://www.codeproject.com/Articles/458052/ULS-Log-Viewer)。 
> - 使用 Microsoft SQL Server Profiler 来帮助捕获或监视数据库错误。有关详细信息，请参阅 [SQL Server Profiler](https://msdn.microsoft.com/library/3ad5f33d-559e-41a4-bde6-bb98792f7f1a.aspx)。 
> - 许多错误代码仅供内部使用。例如，由于第三方开发不支持 **ExchangeSync** 和 **PWA** Web 服务，因此您可能无法查看这两个区域中的方法的错误代码，如 **Rules** 方法和 **StatusReports** 方法。但是，为了完整性，本文中的表包含所有 Project Server 错误代码。 
  
## <a name="table-1-error-code-functional-areas-and-related-number-ranges"></a>表 1. 错误代码功能区和相关编号范围

|Project Server 功能区|错误代码编号范围|
|:-----|:-----|
|[表 3：常规错误代码](#pj15_ErrorCodes_General) <br/> |0 - 99；500 - 999；9131；10000 - 10099；20000 - 20099；26000 - 26099  <br/> |
|[表 4：活动缓存](#pj15_ErrorCodes_ActiveCache) <br/> |12000 - 12099  <br/> |
|[表 5：Active Directory 同步](#pj15_ErrorCodes_ActiveDirectory) <br/> |27000 - 27999  <br/> |
|[表 6：管理员 Web 服务](#pj15_ErrorCodes_Admin) <br/> |16600 - 16699；19011、19012 和 19032；20003；25000 - 25099  <br/> |
|[表 7：存档（备份和还原）](#pj15_ErrorCodes_Archive) <br/> |25000 - 25999；29000 - 29099  <br/> |
|[表 8：分配](#pj15_ErrorCodes_Assignments) <br/> |120 - 199  <br/> |
|[表 9：日历](#pj15_ErrorCodes_Calendar) <br/> |77；13000 - 13999  <br/> |
|[表 10：多维数据集生成服务 (CBS)](#pj15_ErrorCodes_CBS) <br/> |17000 - 17999  <br/> |
|[表 11：签入 - 签出](#pj15_ErrorCodes_CICO) <br/> |10100 - 10199  <br/> |
|[表 12：自定义字段](#pj15_ErrorCodes_CustomFields) <br/> |11500 - 11999  <br/> |
|[表 13：查找表](#pj15_ErrorCodes_LookupTables) <br/> |11000 - 11499  <br/> |
|[表 14：杂项](#pj15_ErrorCodes_Miscellaneous) <br/> |11000 - 11499  <br/> |
|[表 15：通知](#pj15_ErrorCodes_Notifications) <br/> |16000 - 16599  <br/> |
|[表 16：优化器](#pj15_ErrorCodes_Optimizer)  <br/> |29000 - 29999  <br/> |
|[表 17：计划工具](#pj15_ErrorCodes_Planner)（项目组合分析）  <br/> |28000 - 28999  <br/> |
|[表 18：项目](#pj15_ErrorCodes_Projects) <br/> |100 - 499；1000 - 1199；9100 - 9199；23000 - 23999  <br/> |
|[表 19：报告数据服务](#pj15_ErrorCodes_RDS) (RDS)  <br/> |24000 - 24999  <br/> |
|[表 20：资源](#pj15_ErrorCodes_Resources) <br/> |2000 - 2999  <br/> |
|[表 21：资源计划](#pj15_ErrorCodes_ResourcePlans) <br/> |30000 - 30999  <br/> |
|[表 22：规则](#pj15_ErrorCodes_Rules) <br/> |21000 - 21099  <br/> |
|[表 23：安全性](#pj15_ErrorCodes_Security) <br/> |19000 - 19099  <br/> |
|[表 24：服务器事件](#pj15_ErrorCodes_Events) <br/> |19033；22000 - 22999  <br/> |
|[表 25：状态](#pj15_ErrorCodes_Statusing) <br/> |3100 - 3199  <br/> |
|[表 26：状态报表](#pj15_ErrorCodes_StatusReports) <br/> |12100 - 12299  <br/> |
|[表 27：任务](#pj15_ErrorCodes_Tasks) <br/> |7000 - 7099  <br/> |
|[表 28：时间表](#pj15_ErrorCodes_Timesheets) <br/> |3200 - 3299  <br/> |
|[表 29：用户委派](#pj15_ErrorCodes_UserDelegation) <br/> |43000 - 43500  <br/> |
|[表 30：工作流](#pj15_ErrorCodes_Workflow) <br/> |35000 - 35999：工作流  <br/> |
|[表 31：WSSInterop 和 ObjectLinkProvider（SharePoint 集成）](#pj15_ErrorCodes_WSS) <br/> |16400-16499：SharePoint 集成和项目工作区  <br/> 18000 - 18099：对象链接提供程序和 SharePoint 项目导入  <br/> |
   
## <a name="table-2-error-code-table-by-number-range"></a>表 2. 按编号范围排序的错误代码表

|错误代码范围|错误代码表|
|:-----|:-----|
|0 - 99  <br/> |[表 3：常规错误代码](#pj15_ErrorCodes_General)，例外情况是 77 位于[表 9：日历](#pj15_ErrorCodes_Calendar)中 <br/> |
|100 - 119  <br/> |[表 18：项目](#pj15_ErrorCodes_Projects) <br/> |
|120 - 199  <br/> |[表 8：分配](#pj15_ErrorCodes_Assignments) <br/> |
|500 - 999  <br/> |[表 3：常规错误代码](#pj15_ErrorCodes_General) <br/> |
|1000 - 1199  <br/> |[表 18：项目](#pj15_ErrorCodes_Projects) <br/> |
|2000 - 2999  <br/> |[表 20：资源](#pj15_ErrorCodes_Resources) <br/> |
|3100 - 3199  <br/> |[表 25：状态](#pj15_ErrorCodes_Statusing) <br/> |
|3200 - 3299  <br/> |[表 28：时间表](#pj15_ErrorCodes_Timesheets) <br/> |
|7000 - 7099  <br/> |[表 27：任务](#pj15_ErrorCodes_Tasks) <br/> |
|9100 - 9199  <br/> |[表 18：项目](#pj15_ErrorCodes_Projects)，例外情况是 9131 位于[表 3：常规错误代码](#pj15_ErrorCodes_General)中 <br/> |
|10000 - 10099  <br/> |[表 3：常规错误代码](#pj15_ErrorCodes_General) <br/> |
|10100 - 10199  <br/> |[表 11：签入 - 签出](#pj15_ErrorCodes_CICO) <br/> |
|11000 - 11499  <br/> |[表 13：查找表](#pj15_ErrorCodes_LookupTables) <br/> |
|11500 - 11999  <br/> |[表 12：自定义字段](#pj15_ErrorCodes_CustomFields) <br/> |
|12000 - 12099  <br/> |[表 4：活动缓存](#pj15_ErrorCodes_ActiveCache) <br/> |
|12100 - 12299  <br/> |[表 26：状态报表](#pj15_ErrorCodes_StatusReports) <br/> |
|13000 - 13999  <br/> |[表 9：日历](#pj15_ErrorCodes_Calendar) <br/> |
|16000 - 16399  <br/> |[表 15：通知](#pj15_ErrorCodes_Notifications) <br/> |
|16400 - 16499  <br/> |[表 31：WSSInterop 和对象链接提供程序（SharePoint 集成）](#pj15_ErrorCodes_WSS) <br/> |
|16600 - 16699  <br/> |[表 6：管理员 Web 服务](#pj15_ErrorCodes_Admin) <br/> |
|17000 - 17999  <br/> |[表 10：多维数据集生成服务 (CBS)](#pj15_ErrorCodes_CBS) <br/> |
|18000 - 18099  <br/> |[表 31：SharePoint 集成](#pj15_ErrorCodes_WSS) <br/> |
|19000 - 19099  <br/> |[表 23：安全性](#pj15_ErrorCodes_Security)，例外情况是安全性相关代码 19011、19012 和 19032 位于[表 6：管理员 Web 服务](#pj15_ErrorCodes_Admin)中 <br/> |
|20000 - 20099  <br/> |[表 3：常规错误代码](#pj15_ErrorCodes_General)，例外情况是 20003 位于[表 6：管理员 Web 服务](#pj15_ErrorCodes_Admin)中 <br/> |
|21000 - 21099  <br/> |[表 22：规则](#pj15_ErrorCodes_Rules) <br/> |
|22000 - 22999  <br/> |[表 24：服务器事件](#pj15_ErrorCodes_Events) <br/> |
|23000 - 23999  <br/> |[表 18：项目](#pj15_ErrorCodes_Projects) <br/> |
|24000 - 24999  <br/> |[表 19：报告数据服务](#pj15_ErrorCodes_RDS) (RDS)  <br/> |
|25000 - 25999  <br/> |[表 7：存档 （备份和还原）](#pj15_ErrorCodes_Archive)，例外情况是 25004、25006 位于[表 6：管理员 Web 服务](#pj15_ErrorCodes_Admin)中 <br/> |
|26000 - 26099  <br/> |[表 3：常规错误代码](#pj15_ErrorCodes_General) <br/> |
|27000 - 27999  <br/> |[表 5：Active Directory 同步](#pj15_ErrorCodes_ActiveDirectory) <br/> |
|28000 - 28999  <br/> |[表 17：计划工具](#pj15_ErrorCodes_Planner)（项目组合分析）  <br/> |
|29000 - 29999  <br/> |[表 16：优化器](#pj15_ErrorCodes_Optimizer)项目组合分析，例外情况是 29021 位于[表 7：存档](#pj15_ErrorCodes_Archive)中 <br/> |
|30000 - 30999  <br/> |[表 21：资源计划](#pj15_ErrorCodes_ResourcePlans) <br/> |
|31000 - 31999  <br/> 32000 - 32100  <br/> |[表 14：杂项](#pj15_ErrorCodes_Miscellaneous)（正在审核；未使用）  <br/> 项目详细信息页面  <br/> |
|35000 - 35999  <br/> 40000 - 40499  <br/> |[表 30：工作流](#pj15_ErrorCodes_Workflow) <br/> |
|40500 - 40999  <br/> 42000 - 42999  <br/> |[表 14：杂项](#pj15_ErrorCodes_Miscellaneous)（**ExchangeSync**；内部使用）  <br/> Project Web App 时间线  <br/> |
|43000 - 43500  <br/> |[表 29：用户委派](#pj15_ErrorCodes_UserDelegation) <br/> |
|50000 - 51999  <br/> |[表 14：杂项](#pj15_ErrorCodes_Miscellaneous)（数据库错误）  <br/> |

<a name="pj15_ErrorCodes_General"></a>

## <a name="table-3-general-error-codes"></a>表 3. 常规错误代码

|常规错误代码|说明|
|:-----|:-----|
|无错误 = 0；成功 = 0  <br/> |无错误，或者成功。  <br/> |
|GeneralRequestInvalidParameter = 6  <br/> |请求节点或参数之一无效，或在请求的上下文中无效。  <br/> |
|GeneralInvalidValue = 11  <br/> |无效的请求值；例如，指定为 0 的 GUID。  <br/> |
|GeneralStartDateGTorEQFinishDate = 26  <br/> |指定日期范围无效。  <br/> |
|GeneralQueueOperationInProcess = 29  <br/> |操作仍在队列中进行处理的常规错误。  <br/> |
|GeneralUnhandledException = 42  <br/> |发生未经处理的异常。  <br/> |
|GeneralDuplicateGUIDSpecified = 66  <br/> |请求中存在重复 GUID。  <br/> |
|GeneralDateNotValid = 69  <br/> |日期必须位于范围 1/1/1984 到 12/12/2049 中。  <br/> |
|GeneralCostInvalid = 70  <br/> |成本参数无效。  <br/> |
|GeneralWorkInvalid = 71  <br/> |工作参数无效。  <br/> |
|GeneralDurationInvalid = 72  <br/> |持续时间参数无效。  <br/> |
|GeneralUnitsInvalid = 73  <br/> |指定单位无效。  <br/> |
|GeneralOnlyInsertsAllowed = 74  <br/> |仅允许插入。  <br/> |
|GeneralOnlyUpdatesAllowed = 75  <br/> |仅允许更新。  <br/> |
|GeneralSessionInvalid = 76  <br/> |会话参数无效。  <br/> |
|GeneralDependencyUidInvalid = 78  <br/> |依赖项 GUID 无效。  <br/> |
|GeneralNumberInvalid = 79  <br/> |编号无效。  <br/> |
|GeneralInvalidDataStore = 80  <br/> |指定的数据库不存在。 使用 [DataStoreEnum](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.DataStoreEnum.aspx) 中的数据库。  <br/> |
|GeneralDurationOrWorkFormatInvalid = 513  <br/> |工作持续时间或格式无效。  <br/> |
|GeneralRateFormatInvalid = 518  <br/> |费率格式无效。  <br/> |
|GeneralQueueException = 9131  <br/> |异常：队列服务中存在常规错误。  <br/> |
|GeneralItemDoesNotExist = 10000  <br/> |指定的项不存在。  <br/> |
|GeneralLCIDInvalid = 10001  <br/> |区域设置标识符（语言 ID）无效。  <br/> |
|GeneralRowDoesNotExist = 10002  <br/> |**数据表**中的指定行不存在。  <br/> |
|GeneralInvalidColumnValue = 20000  <br/> |**数据表**中的列值无效。  <br/> |
|GeneralInvalidDataRowState = 20001  <br/> |**数据行**状态无效。  <br/> |
|GeneralDuplicatedNames = 20004  <br/> |存在重复的名称。名称必须是唯一的。  <br/> |
|GeneralReadOnlyColumn = 20005  <br/> |列为只读列。  <br/> |
|GeneralReadOnlyRow = 20006  <br/> |行为只读行。  <br/> |
|GeneralNotNullColumn = 20007  <br/> |列不能为 null。  <br/> |
|GeneralObjectAlreadyExists = 20008  <br/> |对象已存在。  <br/> |
|GeneralInvalidObject = 20009  <br/> |对象无效。  <br/> |
|GeneralSecurityAccessDenied = 20010  <br/> |访问因为安全权限被拒绝。  <br/> |
|GeneralInvalidOperation = 20011  <br/> |操作无效。  <br/> |
|GeneralInvalidCharacters = 20012  <br/> |某些字符无效。 除了 TAB 字符之外，项目名称中的下列字符无效：`\ / " : ; < > | , . ' ? * #` <br/> |
|GeneralNameTooLong = 20013  <br/> |名称太长。  <br/> |
|GeneralNameCannotBeBlank = 20014  <br/> |名称不能为空。请勿使用 null 或空字符串。  <br/> |
|GeneralInvalidOperationOnReadOnlyValue = 20016  <br/> |对只读值尝试的操作无效。  <br/> |
|GeneralInvalidDateOverlap = 20018  <br/> |请求包含重叠日期。  <br/> |
|GeneralParameterCannotBeNull = 20020  <br/> |参数不能为 null。  <br/> |
|GeneralDescTooLong = 20021  <br/> |说明太长。  <br/> |
|GeneralCategoryPermissionDenied = 20022  <br/> |类别权限被拒绝。  <br/> |
|GeneralNotLicensed = 20024  <br/> |用户未获得 Project Server 的许可。  <br/> |
|GeneralGlobalPermissionDenied = 20023  <br/> |全局权限被拒绝。  <br/> |
|GeneralActionCanceledByEventHandler = 22000  <br/> |事件处理程序取消了操作。  <br/> |
|GeneralActionCanceledBecauseServerEventServiceNotFound = 22001  <br/> |未找到 Project Server 事件服务。  <br/> |
|GeneralActionCanceledBecauseServerEventServiceProblem = 22002  <br/> |Project Server 事件服务中存在问题。  <br/> |
|GeneralQueueJobFailed = 26000  <br/> |队列作业失败。  <br/> |
|GeneralQueueInvalidJobUID = 26001  <br/> |队列的作业 GUID 无效。  <br/> |
|GeneralQueueInvalidTrackingUID = 26002  <br/> |队列的跟踪 GUID 无效。  <br/> |
|GeneralQueueInvalidJobInfoUID = 26003  <br/> |队列的作业信息 GUID 无效。  <br/> |
|GeneralQueueInvalidCorrelationUID = 26004  <br/> |队列相关 GUID 无效。  <br/> |
|GeneralQueueCorrelationBlocked = 26005  <br/> |队列相关受阻。  <br/> |
|GeneralQueueInvalidMessageType = 26006  <br/> |队列消息类型无效。  <br/> |
|GeneralQueueInvalidJobState = 26007  <br/> |队列作业状态无效。  <br/> |
|GeneralQueueInvalidGroupState = 26008  <br/> |队列中的组状态无效。  <br/> |
|GeneralQueueInvalidGroupPriority = 26009  <br/> |队列中的组优先级无效。  <br/> |
|GeneralQueueInvalidCorrelationPriority = 26010  <br/> |队列中的相关优先级无效。  <br/> |
|GeneralQueueInvalidQueueID = 26011  <br/> |队列标识号无效。  <br/> |
|GeneralQueueInvalidAdminAction = 26012  <br/> |**管理员**操作对队列无效。  <br/> |
|GeneralQueueInvalidStatType = 26013  <br/> |队列状态类型无效。  <br/> |
|GeneralQueueInvalidBlockPolicy = 26014  <br/> |队列阻止策略无效。  <br/> |
|GeneralQueueCannotRetryJob = 26015  <br/> |队列无法重试作业。  <br/> |
|GeneralQueueInvalidSetting = 26016  <br/> |队列的设置无效。  <br/> |
|GeneralQueueInvalidRendezvousUID = 26017  <br/> |队列集合 GUID 无效。  <br/> |
|GeneralDalErrorGettingConnectionStrings = 26018  <br/> |获取数据访问层 (DAL) 的连接字符串时出错。  <br/> |
|GeneralDalErrorConnectingToDatabase = 26019  <br/> |连接到数据库时出现 DAL 错误。  <br/> |
|GeneralDalInvalidArgumentCountCreatingFilter = 26020  <br/> |用于创建筛选器的参数量无效。  <br/> |
|GeneralDataTableCannotBeNull = 26024  <br/> |**数据表**不可为 **null**。  <br/> |
|GeneralDatasetConstraints = 26025  <br/> |**数据集**限制中的错误。  <br/> |
|GeneralInvalidDataSetStructure = 26027  <br/> |**数据集**结构无效。  <br/> |
|GeneralDalNoRowsUpdated = 26028  <br/> |未在数据访问层 (DAL) 中更新任何行。  <br/> |
|GeneralDataTableCannotBeEmpty = 26029  <br/> |**数据表**不可为空。  <br/> |
|GeneralWSSContentDBNotWritable = 26030  <br/> |无法写入 SharePoint 内容数据库。内容数据库为只读或存在网站集级别的锁定。  <br/> |
|GeneralSPValidateFormDigestError = 26031  <br/> |验证 Project Web App 回调中的格式摘要时出错，通常是因为超时。  <br/> |
|GeneralDelegationActiveForCurrentUser = 26032  <br/> |当前用户具有有效委派。Project Professional 的 **WinProj** 服务中的 Web 方法会引发此错误。<br/> |

<a name="pj15_ErrorCodes_ActiveCache"></a>

## <a name="table-4-active-cache"></a>表 4. 活动缓存

|活动缓存错误代码|说明|
|:-----|:-----|
|ActiveCacheInvalidDataFormat = 12000  <br/> |数据格式无效。  <br/> |
|ActiveCacheUnsupportedDataFormatVersion = 12001  <br/> |数据格式版本不受支持。  <br/> |
|ActiveCacheInvalidQueuedMessageType = 12003  <br/> |排队消息类型无效。  <br/> |
|ActiveCacheNullQueuedMessage = 12004  <br/> |排队消息为 null。  <br/> |
|ActiveCacheQueuedMessageExecutionError = 12005  <br/> |排队消息存在执行错误。  <br/> |
|ActiveCacheInvalidDataSize = 12006  <br/> |数据大小无效。  <br/> |
|ActiveCacheQueueJobAlreadyStarted = 12007  <br/> |队列作业已启动。  <br/> |
|ActiveCacheInvalidQueuedMessageFormat = 12008  <br/> |队列中的消息格式无效。  <br/> |
|ActiveCacheUnsupportedQueuedMessageVersion = 12009  <br/> |队列中的消息版本无效。  <br/> |
|ActiveCacheUnsupportedQueueDataType = 12011  <br/> |队列中的数据类型不受支持。  <br/> |
|ActiveCacheInvalidVersionStampForSave = 12012  <br/> |保存操作的版本标记无效。  <br/> |
|ActiveCacheProjectTypeMismatch = 12013  <br/> |项目类型与预期的类型不匹配。  <br/> |
|ActiveCacheDataValidationFailed = 12014  <br/> |数据验证失败。  <br/> |
|ActiveCacheUnsupportedProjectProfessionalVersion = 12015  <br/> |Project Professional 版本不受支持。  <br/> |
|ActiveCacheGeneralSQLException = 12016  <br/> |存在常规 SQL 错误。  <br/> |

<a name="pj15_ErrorCodes_ActiveDirectory"></a>

## <a name="table-5-active-directory-synchronization"></a>表 5. Active Directory 同步

|Active Directory 同步错误代码|说明|
|:-----|:-----|
|AdSyncUpdateTimerJobFailed = 27002  <br/> |更新计时器作业与 Active Directory 目录服务同步失败。  <br/> |
|AdSyncDeleteTimerJobFailed = 27003  <br/> |删除计时器作业与 Active Directory 同步失败。  <br/> |
|AdSyncAdConnectFail = 27006  <br/> |无法与 Active Directory 连接。  <br/> |
|AdMaximumGroupsCountExceeded = 27007  <br/> |超出了最大组计数。  <br/> |
|SRAInvalidVersion = 27300  <br/> |SRA 无效版本。  <br/> |
|SRADelayedUpgradeFailed = 27301  <br/> |SRA 异步更新操作失败。  <br/> |
|(27000 - 27999)  <br/> |Project Server 中未枚举 Active Directory 的其他同步错误。  <br/> |

<a name="pj15_ErrorCodes_Admin"></a>

## <a name="table-6-admin-web-service"></a>表 6. 管理员 Web 服务

|管理员 Web 服务错误代码|说明|
|:-----|:-----|
|AdminViewNameAlreadyExists = 16600  <br/> |视图名称已存在。名称必须是唯一的。  <br/> |
|AdminViewInvalidDividerPosition = 16601  <br/> |分隔线位置无效。  <br/> |
|AdminViewDataWasTampered = 16602  <br/> |数据已更改。  <br/> |
|AdminViewMaxDisplayedFieldsNumberExceeded = 16603  <br/> |显示超出最大字段数。  <br/> |
|AdminViewCannotDeleteDefaultView = 16604  <br/> |无法删除默认视图。  <br/> |
|AdminViewCannotCopyDefaultView = 16605  <br/> |无法复制默认视图。  <br/> |
|AdminLocalCustomFieldInvalid = 19011  <br/> |本地自定义域无效。  <br/> |
|AdminEnterpriseCustomFieldInvalid = 19012  <br/> |企业自定义域无效。  <br/> |
|AdminNTAccountNotFound = 19032  <br/> |未找到 Windows (NTLM) 帐户。  <br/> |
|AdminUnableToMerge = 20003  <br/> |无法合并数据。  <br/> |
|AdminDeleteArchivedProjectsFailed = 25004  <br/> |存档项目的删除操作失败。  <br/> |
|AdminUpdateArchiveScheduleFailed = 25006  <br/> |未能更新存档计划。  <br/> |
|AdminArchiveScheduleFailed = 28018  <br/> |存档计划失败。  <br/> |
|AdminReadArchivedProjectsListFailed = 28019  <br/> |未能读取存档项目的列表。  <br/> |
|AdminReadArchiveScheduleFailed = 28020  <br/> |未能读取存档计划。  <br/> |
|AdminUserAccountNameNull = 28021  <br/> |用户帐户名称为 null。  <br/> |
|AdminIsWindowsUserNull = 28022  <br/> |Windows (NTLM) 用户帐户似乎为 null。  <br/> |
|AdminInvalidTimePeriodState = 28023  <br/> |时间段状态无效。  <br/> |
|AdminGlobalUpdateFailed = 28024  <br/> |调用 **SetServerCurrency** 的过程中，企业全局更新失败。  <br/> |
|AdminGlobalCheckedOut = 28025  <br/> |调用 **SetServerCurrency** 的过程中，企业全局模板已签出。  <br/> |
|AdminInvalidDatabaseTimeout = 28026  <br/> |由于无效的数据库而超时。  <br/> |
|AdminInvalidDatabaseTimeoutType = 28027  <br/> |由于无效的数据库类型而超时。  <br/> |
|AdminInvalidEntityType = 28028  <br/> |实体类型无效。 请参阅 [EntityCollection](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.EntityCollection.aspx)。  <br/> |
|AdminInvalidCompatibilityModeChange = 28029  <br/> |对兼容模式的更改无效。  <br/> |
|AdminInvalidCompatibilityMode = 28030  <br/> |兼容模式无效。  <br/> |
|AdminInvalidProjectProfessionalVersions = 28031  <br/> |Project Professional 版本集无效。  <br/> |
|AdminInvalidProjectProfessionalVersion = 28032  <br/> |Project Professional 版本无效。  <br/> |
|AdminTooManyProjectProfessionalVersions = 28033  <br/> |指定了太多 Project Professional 版本。  <br/> |
|AdminDuplicateProjectProfessionalMajorVersions = 28034  <br/> |Project Professional 主版本中存在重复项。从 Project Professional 2007 开始，您只能为每个主版本指定一个版本。  <br/> |
|AdminInvalidServerFlags = 28035  <br/> |Project Server 设置中的一个或多个标志无效。  <br/> |
|AdminNullProjectProfessionalVersions = 28036  <br/> |一个或多个 Project Professional 版本均为 null。  <br/> |

<a name="pj15_ErrorCodes_Archive"></a>

## <a name="table-7-archive-web-service"></a>表 7. 存档 Web 服务

|存档 Web 服务（备份和还原）错误代码|说明|
|:-----|:-----|
|ArchiveProjectFailure = 25000  <br/> |项目存档操作失败。  <br/> |
|ArchiveProjectsFailed = 25001  <br/> |无法将任何项目保存到存档数据库中。  <br/> |
|ArchiveProjectFailed = 25002  <br/> |无法保存项目存档。  <br/> |
|RestoreProjectFailed = 25003  <br/> |无法还原项目。  <br/> |
|ArchiveResourcesFailed = 25007  <br/> |无法保存资源存档。  <br/> |
|ArchiveCustomFieldsFailed = 25008  <br/> |无法保存自定义域存档。  <br/> |
|RestoreCustomFieldsFailed = 25009  <br/> |无法还原自定义域。  <br/> |
|ArchiveSystemSettingsFailed = 25010  <br/> |无法保存系统设置存档。  <br/> |
|RestoreSystemSettingsFailed = 25011  <br/> |无法还原系统设置。  <br/> |
|ArchiveCategoriesFailed = 25012  <br/> |无法保存安全类别存档。  <br/> |
|RestoreCategoriesFailed = 25013  <br/> |无法还原安全类别。  <br/> |
|ArchiveViewsFailed = 25014  <br/> |无法保存视图存档。  <br/> |
|RestoreViewsFailed = 25015  <br/> |无法还原视图。  <br/> |
|ArchiveGlobalProjectFailed = 25016  <br/> |无法保存企业全局存档。  <br/> |
|RestoreGlobalProjectFailed = 25017  <br/> |无法还原企业全局模板。  <br/> |
|ArchiveInvalidRetentionPolicyValue = 25018  <br/> |存档保留策略值无效。  <br/> |
|ArchiveCustomFieldsFailure = 25019  <br/> |无法读取自定义域存档。  <br/> |
|ArchiveGlobalProjectFailure = 25020  <br/> |无法读取企业全局存档。  <br/> |
|ArchiveResourcesFailure = 25021  <br/> |无法读取资源存档。  <br/> |
|ArchiveSystemSettingsFailure = 25022  <br/> |无法读取系统设置存档。  <br/> |
|ArchiveViewsFailure = 25023  <br/> |无法读取视图存档。  <br/> |
|ArchiveCategoriesFailure = 25024  <br/> |无法读取安全类别存档。  <br/> |
|ResourcePlanPublishFailure = 25025  <br/> |无法发布资源计划。  <br/> |
|RestoreCategoriesFailure = 25026  <br/> |无法从存档还原安全类别。  <br/> |
|RestoreCustomFieldsFailure = 25027  <br/> |无法从存档还原自定义域。  <br/> |
|RestoreGlobalProjectFailure = 25028  <br/> |无法从存档还原企业全局模板。  <br/> |
|RestoreProjectFailure = 25029  <br/> |无法从存档还原项目。  <br/> |
|RestoreResourcesFailure = 25030  <br/> |无法从存档还原资源。  <br/> |
|RestoreSystemSettingsFailure = 25031  <br/> |无法从存档还原系统设置。  <br/> |
|RestoreViewsFailure = 25032  <br/> |无法从存档还原视图。  <br/> |
|ArchiveReadProjectArchiveRetentionSettingFailed = 25033  <br/> |未能读取项目存档保留设置。  <br/> |
|RestoreResourcesFailed = 29021  <br/> |无法还原资源。  <br/> |

<a name="pj15_ErrorCodes_Assignments"></a>

## <a name="table-8-assignment"></a>表 8. 分配

|分配错误代码|说明|
|:-----|:-----|
|AssignmentNotFound = 120  <br/> |未找到工作分配。  <br/> |
|AssignmentWrongTrackingMethod = 122  <br/> |工作分配的跟踪方法错误。  <br/> |
|AssignmentWorkTypeInvalid = 127  <br/> |工作分配工作类型无效。  <br/> |
|AssignmentRateTableInvalid = 130  <br/> |工作分配的费率表无效。  <br/> |
|AssignmentAlreadyExists = 131  <br/> |工作分配已存在。  <br/> |
|AssignmentDuplicateSpecified = 132  <br/> |存在重复的工作分配。  <br/> |
|AssignmentUidInvalid = 133  <br/> |工作分配 GUID 无效。  <br/> |
|AssignmentDelayInvalid = 134  <br/> |工作分配延迟无效。  <br/> |
|AssignmentCannotEditSummaryTask = 135  <br/> |无法为工作分配编辑摘要任务。  <br/> |
|AssignmentInvalid = 136  <br/> |工作分配无效。  <br/> |
|AssignmentFieldsInvalidForBudget = 137  <br/> |工作分配域对预算无效。  <br/> |
|AssignmentAlreadyAssignedToResource = 138  <br/> |资源已具有工作分配。  <br/> |
|AssignmentInvalidOwner = 139  <br/> |工作分配所有者无效。  <br/> |

<a name="pj15_ErrorCodes_Calendar"></a>

## <a name="table-9-calendar"></a>表 9. 日历

|日历错误代码|说明|
|:-----|:-----|
|CalendarUidInvalid = 77  <br/> |日历 GUID 无效。  <br/> |
|CalendarOnlyOneShiftIsNull = 13000  <br/> |仅一次换班为 null。  <br/> |
|CalendarRecurrenceDaysShouldBeNull = 13001  <br/> |重复天数应为 null。  <br/> |
|CalendarRecurrenceMonthDayShouldBeNull = 13002  <br/> |重复月日应为 null。  <br/> |
|CalendarRecurrenceMonthShouldBeNull = 13003  <br/> |重复月应为 null。  <br/> |
|CalendarRecurrenceMonthShouldNotBeNull = 13004  <br/> |重复月不应为 null。  <br/> |
|CalendarRecurrencePositionShouldBeNull = 13005  <br/> |重复位置应为 null。  <br/> |
|CalendarRecurrencePositionShouldNotBeNull = 13006  <br/> |重复位置不应为 null。  <br/> |
|CalendarRecurrenceDaysShouldNotBeNull = 13007  <br/> |重复天数不应为 null。  <br/> |
|CalendarInvalidRecurrenceFrequency = 13008  <br/> |重复频率无效。  <br/> |
|CalendarInvalidRecurrenceType = 13009  <br/> |重复类型无效。  <br/> |
|CalendarInvalidRecurrenceDays = 13010  <br/> |重复天数无效。  <br/> |
|CalendarInvalidCombinationOfMonthDayAndPosition = 13011  <br/> |月、日和位置的组合无效。  <br/> |
|CalendarInvalidRecurrencePosition = 13012  <br/> |重复位置无效。  <br/> |
|CalendarCannotModifyExceptionsForCalendarBeingDeleted = 13013  <br/> |删除日历时无法修改日历例外。  <br/> |
|CalendarExceptionConflict = 13014  <br/> |日历例外中存在冲突。  <br/> |
|CalendarBadDateValue = 13015  <br/> |日期无效。  <br/> |
|CalendarNotFound = 13021  <br/> |未找到日历。  <br/> |
|CalendarAlreadyExists = 13022  <br/> |日历已存在。  <br/> |
|CalendarNameShouldNotBeNull = 13023  <br/> |日历名称为 null。  <br/> |
|CalendarInternalError = 13025  <br/> |日历操作中存在内部错误。  <br/> |
|CalendarNameTooLong = 13027  <br/> |日历名称太长。  <br/> |
|CalendarInvalidCalendarName = 13028  <br/> |日历名称无效。  <br/> |
|CalendarStandardCalendarNotFound = 13031  <br/> |未找到标准日历。  <br/> |
|CalendarInvalidShifts = 13032  <br/> |换班无效。  <br/> |
|CalendarCannotDeleteCalendarUsedByProject = 13033  <br/> |无法删除项目中正使用的日历。  <br/> |
|CalCalendarUniqueIdToDuplicateShouldBeNull = 13035  <br/> |GUID 应为 null 以复制日历。  <br/> |
|CalendarInvalidBaseCalendarUniqueId = 13037  <br/> |基准日历 GUID 无效。  <br/> |
|CalendarInvalidUniqueIdToDuplicate = 13038  <br/> |GUID 对复制日历无效。  <br/> |
|CalendarUnusedCalendarException = 13039  <br/> |日历例外没有对应的日历。如果 **ResourceDataSet.CalendarExceptions** 表中存在条目，但 **Resources** 表中的资源没有 **BaseCalendarUniqueId** 时使用 **UpdateResources** 方法，则会出现此情况。<br/> |
|CalendarCannotDeleteStandardCalendar = 13040  <br/> |无法删除标准日历。  <br/> |
|CalendarCannotRenameStandardCalendar = 13041  <br/> |无法重命名标准日历。  <br/> |
|CalendarCannotDeleteCalendarUsedByEnterpriseResource = 13042  <br/> |日历正由企业资源使用，无法删除它。  <br/> |
|CalendarFilterInvalid = 13043  <br/> |筛选器对日历无效。  <br/> |

<a name="pj15_ErrorCodes_CBS"></a>

## <a name="table-10-cubeadmin-and-cube-build-service"></a>表 10. CubeAdmin 和多维数据集生成服务

|CubeAdmin 和多维数据集生成服务 (CBS) 错误代码|说明|
|:-----|:-----|
|CBSGeneralFailure = 17001  <br/> |多维数据集生成服务 (CBS) 出现故障。这可能是许多不同原因导致的常规错误代码。  <br/> |
|CBSDsoNotInstalled = 17002  <br/> |CBS 需要为 Analysis Services 安装决策支持对象 (DSO) 组件。  <br/> |
|CBSASConnectionFailure = 17003  <br/> |CBS 未能连接到 Analysis Services 服务器。  <br/> |
|CBSOlapProcessingFailure = 17004  <br/> |OLAP 多维数据集处理失败。  <br/> |
|CBSMetadataProcessingFailure = 17005  <br/> |多维数据集元数据的处理失败。  <br/> |
|CBSASServerLockTimeOut = 17006  <br/> |Analysis Services 服务器锁定超时。  <br/> |
|CBSOlapDatabaseSetupFailure = 17007  <br/> |OLAP 多维数据集数据库的安装失败。  <br/> |
|CBSASEntityLimitation = 17008  <br/> |超出了 Analysis Services 可使用的实体数量。  <br/> |
|CBSRequestInvalidArguments = 17009  <br/> |CBS 请求中的一个或多个参数无效。  <br/> |
|CBSQueueingRequestFailed = 17010  <br/> |CBS 未能将作业提交到队列。  <br/> |
|CBSUpdateCubeCalculatedMeasureDefintionError = 17011  <br/> |多维数据集计算成员中存在错误。  <br/> |
|CBSAttemptToOverwrite = 17013  <br/> |无法覆盖多维数据集中的数据。  <br/> |
|CBSCustomFieldCannotBeAddedAsDimension = 17014  <br/> |自定义域不能是多维数据集维度。  <br/> |
|CBSCustomFieldFailedToBeAddedAsDimension = 17015  <br/> |未能将自定义域作为多维数据集中的维度添加。  <br/> |
|CBSCustomFieldCannotBeAddedAsMeasure = 17016  <br/> |自定义域不能是多维数据集度量。  <br/> |
|CBSCustomFieldFailedToBeAddedAsMeasure = 17017  <br/> |未能将自定义域作为多维数据集中的度量添加。  <br/> |
|CBSDsoTranslatorNotFound = 17018  <br/> |未找到决策支持对象转换器。  <br/> |
|CBSUpdateOlapDBOperationFailure = 17019  <br/> |未能更新 OLAP 数据库。  <br/> |
|CBSOlapDBInvalidArguments = 17020  <br/> |OLAP 数据库的一个或多个参数无效。  <br/> |
|CBSOlapDatabaseReadSettingListFailed = 17021  <br/> |未能读取 OLAP 数据库设置的列表。  <br/> |
|CBSOlapDatabaseReadSettingFailed = 17022  <br/> |未能读取 OLAP 数据库设置。  <br/> |
|CBSDeleteOlapDatabaseSetting = 17023  <br/> |删除 OLAP 数据库设置时出错。  <br/> |
|CBSSetDefaultOlapDatabase = 17024  <br/> |设置默认 OLAP 数据库时出错。  <br/> |
|CBSSetOlapDatabaseEnabled = 17025  <br/> |启用 OLAP 数据库时出错。  <br/> |
|CBSGetDefaultOlapDatabase = 17026  <br/> |获取默认 OLAP 数据库时出错。  <br/> |
|CBSCustomFieldFailedToBeAddedAsDimensionOrMeasure = 17027  <br/> |无法将自定义域作为维度或度量添加。  <br/> |
|CBSOlapDatabaseAssocFieldsSettings = 17028  <br/> |OLAP 数据库关联域设置中存在错误。  <br/> |
|CBSUpdateOlapDBOperationDuplicateOrFailure = 17029  <br/> |OLAP 数据库更新操作出现故障或重复。  <br/> |
|CBSErrorReadingDefaultDatabase = 17030  <br/> |读取默认 OLAP 数据库时出错。  <br/> |
|CBSCreateOlapDBOperationFailure = 17031  <br/> |未能创建 OLAP 数据库操作。  <br/> |
|CBSSetCubeFieldsSettingsFromListForGroupMeasureFailed = 17032  <br/> |未能设置多维数据集域的组度量设置的列表。  <br/> |
|CBSErrorReadingCubeDepartments = 17033  <br/> |读取 OLAP 多维数据集中的部门时出错。  <br/> |
|CBSErrorMaxOlapDatabaseCountReached = 17034  <br/> |已达到最大 OLAP 数据库计数。  <br/> |
|CBSErrorReadingCubeFieldsSettings = 17035  <br/> |读取多维数据集域设置时出错。  <br/> |

<a name="pj15_ErrorCodes_CICO"></a>

## <a name="table-11-check-in-and-check-out"></a>表 11. 签入和签出

|签入 - 签出错误代码|说明|
|:-----|:-----|
|CICOCheckedOutToOtherUser = 10100  <br/> |已签出给另一个用户。  <br/> |
|CICOAlreadyCheckedOutToYou = 10101  <br/> |已签出给您。  <br/> |
|CICONotCheckedOut = 10102  <br/> |未签出。  <br/> |
|CICOCheckedOutInOtherSession = 10103  <br/> |在另一个会话中进行签出。  <br/> |
|CICOInvalidSessionGuid = 10104  <br/> |会话 GUID 无效。  <br/> |
|CICOAlreadyCheckedOutInSameSession = 10105  <br/> |已在另一个会话中进行签出。  <br/> |
|CICOCannotCheckOutVisibilityModeProjectWithMppInDocLib = 10106  <br/> |无法在文档库中查看带有 mpp 文件的可见性模式项目。  <br/> |

<a name="pj15_ErrorCodes_CustomFields"></a>

## <a name="table-12-custom-field"></a>表 12. 自定义字段

|自定义字段错误代码|说明|
|:-----|:-----|
|CustomFieldInvalidPropertyType = 11500  <br/> |属性类型无效。  <br/> |
|CustomFieldInvalidScope = 11503  <br/> |自定义域范围无效。  <br/> |
|CustomFieldScopesMustBeIdentical = 11504  <br/> |范围必须相同。  <br/> |
|CustomFieldInvalidEntityUID = 11505  <br/> |自定义域实体 GUID 无效。  <br/> |
|CustomFieldHasInvalidPropertiesForNonLookupTableCF = 11506  <br/> |属性对没有查阅表格的自定义域无效。  <br/> |
|CustomFieldNonExistentWeightsTableUID = 11507  <br/> |权重表 GUID 不存在。  <br/> |
|CustomFieldInvalidName = 11508  <br/> |自定义域名称无效。  <br/> |
|CustomFieldInvalidDefault = 11510  <br/> |自定义域的默认值无效。  <br/> |
|CustomFieldInvalidLookupTableUID = 11511  <br/> |查阅表格 GUID 无效。  <br/> |
|CustomFieldTypeDoesNotMatchLookupTableMask = 11512  <br/> |自定义域类型与查阅表格掩码不匹配。  <br/> |
|CustomFieldCannotHaveNonLeafNodeDefault = 11513  <br/> |自定义域默认值必须是叶节点。  <br/> |
|CustomFieldMatchingOnlyAvailableForResources = 11514  <br/> |匹配的自定义域仅可用于资源。  <br/> |
|CustomFieldUIDCannotMatchLookupTableUID = 11516  <br/> |GUID 与查阅表格 GUID 不匹配。  <br/> |
|CustomFieldUIDAlreadyExists = 11517  <br/> |自定义域 GUID 已存在。  <br/> |
|CustomFieldIDAlreadyExists = 11518  <br/> |自定义域标识号已存在。  <br/> |
|CustomFieldNameAlreadyExists = 11519  <br/> |自定义域名称已存在。  <br/> |
|CustomFieldInvalidEntity = 11520  <br/> |实体对自定义域无效。  <br/> |
|CustomFieldMaskDoesNotMatchEntityType = 11521  <br/> |代码掩码与实体类型不匹配。  <br/> |
|CustomFieldLowerOrderBitsOutOfRange = 11522  <br/> |低序位超出范围。  <br/> |
|CustomFieldInvalidMaxValues = 11523  <br/> |一个或多个最大值无效。  <br/> |
|CustomFieldCannotModifyCertainValuesOnceDefined = 11524  <br/> |特定值定义后便无法修改。  <br/> |
|CustomFieldNonExistentPID = 11526  <br/> |自定义域属性标识号不存在。  <br/> |
|CustomFieldCannotChangeBuiltInFields = 11527  <br/> |无法更改 Project Server 内置域，如成本类型、状态和 RBS。  <br/> |
|CustomFieldSecondaryUidCannotEqualUid = 11528  <br/> |辅助 GUID 不能等于主 GUID。  <br/> |
|CustomFieldCannotHaveSecondaryUIDorIDForThisEntityType = 11529  <br/> |自定义域不能具有辅助 GUID 或此实体类型的 GUID。  <br/> |
|CustomFieldNameMatchesIntrinsicField = 11530  <br/> |自定义域名称与内部域匹配。  <br/> |
|CustomFieldInvalidAggregationType = 11531  <br/> |聚合类型无效。  <br/> |
|CustomFieldProjectFormulaFieldsMustUseFormulaAggregation = 11532  <br/> |项目公式域必须使用公式聚合。  <br/> |
|CustomFieldMustSpecifyEitherIDorUID = 11700  <br/> |必须指定自定义域标识号或 GUID。  <br/> |
|CustomFieldInvalidID = 11701  <br/> |自定义域标识号无效。  <br/> |
|CustomFieldInvalidUID = 11702  <br/> |自定义域 GUID 无效。  <br/> |
|CustomFieldInvalidType = 11703  <br/> |自定义域类型无效。  <br/> |
|CustomFieldInvalidTypeColumnFilledIn = 11704  <br/> |自定义字段类型列值无效。 请参阅 [WCF 的错误代码示例](#pj15_ErrorCodes_WCFExample)中的示例。  <br/> |
|CustomFieldCodeValueDoesNotMatchLookupTable = 11706  <br/> |代码值与查阅表格不匹配。  <br/> |
|CustomFieldCodeValueIsNotLeafNode = 11707  <br/> |代码值不是查阅表格的叶节点。  <br/> |
|CustomFieldRowAlreadyExists = 11708  <br/> |自定义域行已存在。  <br/> |
|CustomFieldRowDoesNotMatchCorrespondingDefinitionInDB = 11710  <br/> |自定义域行与数据库定义不匹配。  <br/> |
|CustomFieldCodeValueAlreadyUsed = 11711  <br/> |代码值已被使用。  <br/> |
|CustomFieldMaxValuesExceeded = 11712  <br/> |超出了最大自定义域值。  <br/> |
|CustomFieldRequiredValueNotProvided = 11713  <br/> |未提供必填自定义域值。 请参阅 [WCF 的错误代码示例](#pj15_ErrorCodes_WCFExample)中的示例。  <br/> |
|CustomFieldCannotChangeLookupTable = 11715  <br/> |无法更改自定义域查阅表格。  <br/> |
|CustomFieldFilterInvalid = 11716  <br/> |自定义域筛选器无效。  <br/> |
|CustomFieldRolldownInvalidOnFormulaFields = 11717  <br/> |公式自定义域上不能出现下滚。  <br/> |
|CustomFieldFormulaFieldCannotBeRequired = 11718  <br/> |公式域不能是必需的。  <br/> |
|CustomFieldFormulaFieldCannotBeWorkflowControlled = 11719  <br/> |公式域不能受工作流控制。  <br/> |
|CustomFieldCannotSetValueOnFormulaFields = 11720  <br/> |无法设置公式域上的值。  <br/> |
|CustomFieldNewPerRequestLimitExcedeed = 11721  <br/> |超出新自定义域的请求限制。 该限制是一个请求中的 [NEW_CF_PER_REQUEST_LIMIT](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.CustomField.NEW_CF_PER_REQUEST_LIMIT.aspx)。  <br/> |
|CustomFieldNameIsReservedName = 11722  <br/> |自定义域名称不能是保留名称。  <br/> |
|CustomFieldNameInvalidForOlapMeasure = 11723  <br/> |自定义域名称对 OLAP 多维数据集度量无效。  <br/> |
|CustomFieldNameInvalidForOlapDimension = 11724  <br/> |自定义域名称对 OLAP 多维数据集维度无效。  <br/> |
|CustomFieldSettingsInvalidForOlapMeasure = 11725  <br/> |自定义域设置对 OLAP 多维数据集度量无效。  <br/> |
|CustomFieldSettingsInvalidForOlapDimension = 11726  <br/> |自定义域设置对 OLAP 多维数据集维度无效。  <br/> |
|CustomFieldCannotAddRelativeImportanceField = 11727  <br/> |无法添加相对重要性域。  <br/> |
|CustomFieldCannotAddProjectImpactField = 11728  <br/> |无法添加项目影响域。  <br/> |
|CustomFieldInvalidDepartmentUid = 11731  <br/> |自定义域中的部门 GUID 无效。  <br/> |
|CustomFieldCannotModifyDepartmentUidOnBuiltinFields = 11732  <br/> |无法对内置自定义域修改部门 GUID。  <br/> |
|CustomFieldCannotHaveBothLookupTableAndMultilineText = 11733  <br/> |自定义域不能同时包含查阅表格和多行文本。  <br/> |
|CustomFieldCannotHaveBothFormulaAndMultilineText = 11734  <br/> |自定义域不能同时包含公式和多行文本。  <br/> |
|CustomFieldDescriptionExceedsLimit = 11735  <br/> |自定义域说明太长。**MD_PROP_DESCRIPTION** 属性的最大长度为 1000 个字符。<br/> |
|CustomFieldOnlyTextFieldsCanHaveMultilineText = 11736  <br/> |仅文本自定义域可具有多行文本。  <br/> |
|CustomFieldOnlyProjectFieldsCanHaveMultilineText = 11737  <br/> |仅项目自定义域可具有多行文本。  <br/> |
|CustomFieldCannotChangeWorkflowControlledBehaviorForNonProjectCustomFields = 11738  <br/> |自定义域无法更改工作流控制的非项目自定义域的行为。  <br/> |
|CustomFieldIsWorkflowControlledAndCannotBeChanged = 11739  <br/> |自定义域由工作流控制，无法更改。  <br/> |
|CustomFieldCannotHaveRequiredFlagWhenWorkflowControlledFlagIsSet = 11740  <br/> |自定义域受工作流控制时不能是必需的。  <br/> |
|CustomFieldFormulaCreatesCircularReference = 11742  <br/> |自定义域公式将创建循环引用。  <br/> |
|CustomFieldFormulaContainsInvalidFieldReference = 11743  <br/> |自定义域公式包含无效的域引用。  <br/> |
|CustomFieldFormulaContainsErrors = 11744  <br/> |自定义域公式包含一个或多个错误。  <br/> |
|CustomFieldLocalCustomFieldNotDefined = 11745  <br/> |未定义本地自定义域。  <br/> |
|CustomFieldGraphicalIndicatorContainsErrors = 11746  <br/> |自定义域图形指示器包含错误。  <br/> |
|CustomFieldGraphicalIndicatorContainsInvalidFieldReference = 11747  <br/> |自定义域图形指示器包含无效的域引用。  <br/> |
|CustomFieldGraphicalIndicatorTypeMismatch = 11748  <br/> |自定义域图形指示器存在类型不匹配。  <br/> |
|CustomFieldFormulaFieldCannotReferenceWorkflowControlledField = 11749  <br/> |公式中的域无法引用工作流控制的域。  <br/> |
|CustomFieldWorkflowCustomFieldBeingReferencedByFormula = 11750  <br/> |公式正在尝试引用工作流自定义域。  <br/> |

<a name="pj15_ErrorCodes_LookupTables"></a>

## <a name="table-13-lookup-table"></a>表 13. 查阅表格

|查阅表格错误代码|说明|
|:-----|:-----|
|LookupTableMaskNotDefined = 11000  <br/> |未定义查阅表格代码掩码。  <br/> |
|LookupTableMaskHasTooManyValues = 11001  <br/> |查阅表格代码掩码具有太多值。  <br/> |
|LookupTableMaskHasGaps = 11002  <br/> |查阅表格代码掩码具有差距。  <br/> |
|LookupTableMaskSequenceTypeLimitedToOneLevelDeep = 11003  <br/> |将代码掩码序列类型限制为一个级别。  <br/> |
|LookupTableMaskSequenceTypeInvalid = 11004  <br/> |代码掩码序列类型无效。  <br/> |
|LookupTableMaskSequenceRequiresAnyLength = 11005  <br/> |代码掩码序列需要 _Any_ 的长度。  <br/> |
|LookupTableMaskSeparatorTooLong = 11006  <br/> |代码掩码分隔符具有太多字符。  <br/> |
|LookupTableMaskLevelMustBeBlankAcrossLCIDs = 11007  <br/> |区域设置标识符（语言 ID）中的代码掩码级别必须为空。  <br/> |
|LookupTableMaskSeparatorInvalid = 11008  <br/> |代码掩码分隔符无效。  <br/> |
|LookupTableMaskBlankSeparatorInvalidAfterAnyLengthSequence = 11009  <br/> |_Any_ 的序列长度后的空分隔符无效。  <br/> |
|LookupTableMaskSequenceLengthInvalid = 11010  <br/> |代码掩码序列长度无效。  <br/> |
|LookupTableMaskLevelMustBeOneOrMore = 11011  <br/> |代码掩码级别必须为 1 或更大值。  <br/> |
|LookupTableItemDoesNotFitMask = 11050  <br/> |查阅表格项不适合于代码掩码定义。  <br/> |
|LookupTableItemContainsSeparator = 11051  <br/> |查阅表格项包含分隔符。  <br/> |
|LookupTableItemFullValueTooLong = 11052  <br/> |查阅表格项的完整值太长。  <br/> |
|LookupTableDuplicateSiblingsDisallowed = 11053  <br/> |查阅表格中不允许存在重复的同级。  <br/> |
|LookupTableSortOrderIndexInvalid = 11054  <br/> |查阅表格排序顺序索引无效。  <br/> |
|LookupTableSortOrderIndexDuplicate = 11055  <br/> |查阅表格排序顺序索引重复。  <br/> |
|LookupTableSortOrderTypeInvalid = 11056  <br/> |查阅表格排序顺序类型无效。  <br/> |
|LookupTableSortOrderMustComeAfterParentSortOrder = 11057  <br/> |排序顺序必须位于父排序顺序之后。  <br/> |
|LookupTableSortOrderMustComeBeforeParentNextSiblingSortOrder = 11058  <br/> |排序顺序必须位于下一同级的父排序顺序之前。  <br/> |
|LookupTableInvalidCookieLength = 11060  <br/> |查阅表格的 cookie 长度无效。  <br/> |
|LookupTableMustHaveValuesForPrimaryLCIDorJustOneValue = 11061  <br/> |查阅表格必须具有主区域设置标识符（语言 ID）的值，或仅具有一个值。例如，当您创建多语言查阅表格时，仅为每个级别添加一个掩码值，或首先为主 LCID 添加值。  <br/> |
|LookupTableLCIDNotSupportedInLookupTableLanguages = 11062  <br/> |查阅表格语言中未包含区域设置标识符（语言 ID）。  <br/> |
|LookupTableInvalidDescriptionLength = 11063  <br/> |查阅表格项的说明长度无效。  <br/> |
|LookupTableCannotChangeBuiltInTables = 11064  <br/> |无法更改内置查阅表格。  <br/> |
|LookupTableCannotChangeTypeOnceCreated = 11065  <br/> |查阅表格创建之后便无法更改查阅表格类型。  <br/> |
|LookupTableCannotDeleteLTWithDependantCustomField = 11066  <br/> |无法删除自定义域中使用的查阅表格。  <br/> |
|LookupTableAllLevelsNotFilled = 11067  <br/> |必须填写所有查阅表格级别。  <br/> |
|LookupTableDuplicateName = 11068  <br/> |查阅表格名称必须是唯一的。  <br/> |
|LookupTableInvalidName = 11069  <br/> |查阅表格名称无效。  <br/> |
|LookupTableDuplicateSiblingPhoneticsDisallowed = 11071  <br/> |查阅表格中不能包含重复的同级拼音。  <br/> |
|LookupTableItemInvalidLookupTable = 11073  <br/> |查阅表格中的项无效。  <br/> |
|LookupTableInvalidPhoneticsLength = 11074  <br/> |拼音域的长度无效。  <br/> |
|LookupTableAlreadyExists = 11076  <br/> |查阅表格已存在。  <br/> |
|LookupTableInvalidUID = 11078  <br/> |查阅表格 GUID 无效。  <br/> |
|LookupTableFilterInvalid = 11079  <br/> |查阅表格筛选器无效。  <br/> |
|LookupTableLanguageParameterInvalidWithXmlFilter = 11080  <br/> |语言参数与查阅表格 _xmlFilter_ 参数一起使用时无效。  <br/> |
|LookupTableInvalidParentStructUid = 11081  <br/> |查阅表格父结构的 GUID 无效。  <br/> |
|LookupTableItemContainsListSeparator = 11082  <br/> |查阅表格项包含列表分隔符。  <br/> |
   
表 14 中的错误代码包含项目详细信息页 (PDP)、Exchange 同步、Project Web App 日程表和数据库错误的项。 表 14 中的许多杂项错误代码供内部使用。
  
> [!NOTE]
> Project Server 2013 中未使用审核错误代码。 

<a name="pj15_ErrorCodes_Miscellaneous"></a>

## <a name="table-14-miscellaneous-error-codes"></a>表 14. 杂项错误代

|杂项错误代码|说明|
|:-----|:-----|
|AuditingUpdateFailure = 31000  <br/> |未使用。  <br/> |
|AuditingCannotDeleteFeature = 31001  <br/> |未使用。  <br/> |
|AuditingCannotAddFeature = 31002  <br/> |未使用。  <br/> |
|AuditingFeatureIsNoLongerAudited = 31003  <br/> |未使用。  <br/> |
|AuditingItemIsNotYetAvailable = 31004  <br/> |未使用。  <br/> |
|AuditingInvalidFeatureUid = 31005  <br/> |未使用。  <br/> |
|AuditingInvalidStoreForSelectedFeature = 31006  <br/> |未使用。  <br/> |
|AuditingInvalidStore = 31007  <br/> |未使用。  <br/> |
|AuditingVersionNameTooLong = 31008  <br/> |未使用。  <br/> |
|AuditingBeginVersionFailure = 31009  <br/> |未使用。  <br/> |
|AuditingEndVersionFailure = 31010  <br/> |未使用。  <br/> |
|ProjectDetailPagesStrategicImpactRatingRequired = 32000  <br/> |项目详细信息页需要战略影响评定。  <br/> |
|ProjectDetailPagesMissingPDPLinks = 32001  <br/> |缺少指向项目详细信息页的链接。  <br/> |
|ProjectDetailPagesUnavailableWorker = 32002  <br/> |项目明细加载失败。无可用工作进程。  <br/> |
|ProjectDetailPagesFailedToLoadProjectInWorker = 32003  <br/> |工作进程未能加载。  <br/> |
|AppPermissionInvalidAppPermissionId = 32300  <br/> |应用程序权限 ID 存在问题。  <br/> |
|InvariantValidationPSIFailed = 40000  <br/> |如果任何私有方法返回 **ValidationMethodFailed**，则由 **PWA** 方法返回。内部使用。<br/> |
|ValidationMethodFailed = 40001  <br/> |当检测到数据库不一致时，由私有 **PWA** 方法返回。内部使用。<br/> |
|GeneralExchangeSyncError = 40500  <br/> |Microsoft Exchange 同步中存在常规错误。内部使用。  <br/> |
|ExchangeSyncRootFolderCreationFailed = 40501  <br/> |未能创建 Microsoft Exchange 同步的根文件夹。  <br/> |
|ExchangeSyncTaskFolderCreationFailed = 40502  <br/> |未能创建任务文件夹。  <br/> |
|ExchangeSyncCouldNotGetRootFolder = 40503  <br/> |无法获取根文件夹。  <br/> |
|ExchangeSyncCouldNotLoadTaskObject = 40504  <br/> |无法加载任务对象。  <br/> |
|ExchangeSyncNewExchangeTaskCreationFailed = 40505  <br/> |Exchange 同步的新任务创建失败。  <br/> |
|ExchangeSyncFailedToUpdateCacheForUser = 40506  <br/> |未能为用户更新 Exchange 同步缓存。  <br/> |
|ExchangeSyncFailedToUpdateExchangeTask = 40507  <br/> |未能更新 Microsoft Exchange 中的任务。  <br/> |
|ExchangeSyncSubscriptionUpdateFailed = 40508  <br/> |未能更新 Exchange 同步订阅。  <br/> |
|ExchangeSyncEWSUrlFailed = 40509  <br/> |Microsoft Exchange Web 服务 URL 失败。  <br/> |
|ExchangeSyncExchangeUrlRefreshFailed = 40510  <br/> |未能刷新 Exchange URL。  <br/> |
|ExchangeSyncExchangeSubscriptionUpdateForUserFailed = 40511  <br/> |未能为用户更新 Exchange 订阅。  <br/> |
|ExchangeSyncGeneralProcessingFailure = 40512  <br/> |Microsoft Exchange 同步中的常规处理出现故障。  <br/> |
|ExchangeSyncDeletionOfTasksInExchangeFailure = 40513  <br/> |未能删除 Exchange 同步中的任务。  <br/> |
|ExchangeSyncAttemptedSyncOfInvalidConfiguredResource = 40514  <br/> |已尝试将资源与无效的配置同步。  <br/> |
|ExchangeSyncRetrievalOfEWSUrlCausedException = 40515  <br/> |检索 Exchange Web 服务期间出现异常。  <br/> |
|TimelineViewDataDoesNotExist = 42000  <br/> |Project Web App 的日程表视图中不存在数据。  <br/> |
|DatabaseUndefinedError = 50000  <br/> |未定义数据库。  <br/> |
|DatabaseCannotInsertDuplicateKeyError = 50001  <br/> |数据库不能插入重复键。  <br/> |

<a name="pj15_ErrorCodes_Notifications"></a>

## <a name="table-15-notification"></a>表 15. 通知

|通知错误代码|说明|
|:-----|:-----|
|NotificationReminderUnknown = 16050  <br/> |提醒通知未知。  <br/> |
|NotificationReminderParentNotSubscribed = 16051  <br/> |没有对提醒通知父级的订阅。  <br/> |
|NotificationReminderParentNotFound = 16052  <br/> |未找到提醒通知的父级。  <br/> |
|NotificationReminderChildStillSubscribed = 16053  <br/> |仍存在对通知提醒子级的订阅。  <br/> |
|NotificationReminderChildNotFound = 16054  <br/> |未找到提醒通知的子级。  <br/> |
|NotificationEMailDeliveryFailed = 16080  <br/> |通知电子邮件传递失败。  <br/> |
|NotificationQueueMessageFailed = 16082  <br/> |通知队列消息失败。  <br/> |
|NotificationXSLTTransformationError = 16084  <br/> |通知 XSLT 转换中存在错误。  <br/> |
   
表 16 中的所有错误代码均针对优化器，它是项目组合分析中使用的组件。

<a name="pj15_ErrorCodes_Optimizer"></a>

## <a name="table-16-optimizer-project-portfolio-analysis"></a>表 16. 优化器（项目组合分析）

|优化器错误代码|说明|
|:-----|:-----|
|OptimizerDepInvalidDepType = 29000  <br/> |[OptimizerDependencyDataSet.OptimizerDependenciesRow](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.OptimizerDependencyDataSet.OptimizerDependenciesRow.aspx) 中的优化器 **DEPENDENCY_TYPE** 值无效。 请参阅 [Optimizer.DependencyTypes](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.Optimizer.DependencyTypes.aspx)。  <br/> |
|OptimizerDepInvalidEntityType = 29001  <br/> |实体类型无效。 请参阅 [Entities](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.EntityCollection.Entities.aspx) 属性。  <br/> |
|OptimizerDepInvalidPosition = 29003  <br/> |[POSITION](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.OptimizerDependencyDataSet.OptimizerDependencyDetailsRow.POSITION.aspx) 值无效。  <br/> |
|OptimizerDepDuplicateDependentProjects = 29004  <br/> |[OptimizerDependencyDataSet.OptimizerDependencyDetailsDataTable](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.OptimizerDependencyDataSet.OptimizerDependencyDetailsDataTable.aspx) 中存在重复的项目。  <br/> |
|OptimizerDepInvalidDependency = 29005  <br/> |优化器依赖关系无效。  <br/> |
|OptimizerDepCircularDependency = 29006  <br/> |存在循环依赖关系。  <br/> |
|OptimizerCannotDeleteDependency = 29007  <br/> |无法删除依赖关系。  <br/> |
|OptimizerCannotCreateDependency = 29008  <br/> |无法创建依赖关系。  <br/> |
|OptimizerCannotUpdateDependency = 29009  <br/> |无法更新依赖关系。  <br/> |
|OptimizerCannotCreateMultipleDependencies = 29010  <br/> |无法创建多个依赖关系。  <br/> |
|OptimizerCannotUpdateMultipleDependencies = 29011  <br/> |无法更新多个依赖关系。  <br/> |
|OptimizerEngineMatrixNotFilled = 29100  <br/> |优化器没有足够的数据用于计算。  <br/> |
|OptimizerEngineCustomFieldIsNotAConstraint = 29101  <br/> |自定义域不是优化器的约束。  <br/> |
|OptimizerCouldNotCalculatePrioritiesFromCustomFields = 29102  <br/> |无法计算指定自定义域中的优先级。  <br/> |
|OptimizerEngineBinaryInfeasibleSolution = 29103  <br/> |优化器计算生成不可行的解决方案。  <br/> |
|OptimizerEngineBinaryNumericalError = 29104  <br/> |优化器计算中存在数字错误。  <br/> |
|OptimizerEngineBinaryTimedOut = 29105  <br/> |优化器计算超时。  <br/> |
|OptimizerEngineBinaryMaxedIterations = 29106  <br/> |优化器计算达到最大迭代数。  <br/> |
|OptimizerEngineBinarySubOptimal = 29107  <br/> |优化器计算结果并非最佳。  <br/> |
|OptimizerEngineBinaryInternalError = 29108  <br/> |优化器计算中存在内部错误。  <br/> |
|OptimizerInvalidRange = 29200  <br/> |优化器的数据范围无效。  <br/> |
|OptimizerNonNormalizedWeights = 29201  <br/> |[AnalysisDataSet.AnalysisPriorityDataDataTable](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.AnalysisDataSet.AnalysisPriorityDataDataTable.aspx) 中的 **WEIGHT** 值未标准化。  <br/> |
|OptimizerCannotEditPrioritization = 29300  <br/> |无法编辑驱动因素优先顺序。  <br/> |
|OptimizerCannotDeletePrioritization = 29301  <br/> |无法删除驱动因素优先顺序。  <br/> |
|OptimizerCannotCreatePrioritization = 29302  <br/> |无法创建驱动因素优先顺序。  <br/> |
|OptimizerCannotUpdatePrioritization = 29303  <br/> |无法更新驱动因素优先顺序。  <br/> |
|OptimizerCannotCalculateDriverPriorities = 29304  <br/> |无法计算驱动因素优先顺序。  <br/> |
|OptimizerCannotCreateMultiplePrioritizations = 29305  <br/> |无法创建多个驱动因素优先顺序。  <br/> |
|OptimizerCannotUpdateMultiplePrioritizations = 29306  <br/> |无法更新多个驱动因素优先顺序。  <br/> |
|OptimizerDriverRelationsNotFilled = 29307  <br/> |DriverRelationsRow 数据不完整。  <br/> |
|OptimizerDriversNotFilled = 29308  <br/> |在解决方案的项目驱动因素中没有足够信息。  <br/> |
|OptimizerDriverRelationsInvalidInversedValue = 29309  <br/> |[DriverPrioritizationDataSet.DriverRelationsRow](https://msdn.microsoft.com/library/WebSvcDriver.DriverPrioritizationDataSet.DriverRelationsRow.aspx) 中存在反转值。  <br/> |
|OptimizerCannotCreatePrioritizationUsingInactiveDrivers = 29310  <br/> |[DriverPrioritizationDataSet.DriverRelationsRow](https://msdn.microsoft.com/library/WebSvcDriver.DriverPrioritizationDataSet.DriverRelationsRow.aspx) 中存在指定的不活动磁盘。 检查 **DRIVER1_UID** 和 **DRIVER2_UID** 属性。  <br/> |
|OptimizerCannotChangePrioritizationType = 29311  <br/> |无法更改优先顺序类型。  <br/> |
|OptimizerCannotSpecifyPriorityValuesForCalculatedPrioritizations = 29312  <br/> |如果计算优先级，则无法指定优先级值。  <br/> |
|OptimizerCannotNormalizePriorityValues = 29313  <br/> |无法标准化优先级值。  <br/> |
|OptimizerTooManyDriversInPrioritization = 29314  <br/> |优先顺序中的业务驱动因素太多。  <br/> |
|OptimizerInvalidProjectImpactValue = 29400  <br/> |项目影响值无效。  <br/> |
|OptimizerCannotDeleteDriver = 29401  <br/> |无法删除项目驱动因素。  <br/> |
|OptimizerCannotCreateDriver = 29402  <br/> |无法创建项目驱动因素。  <br/> |
|OptimizerCannotUpdateDriver = 29403  <br/> |无法更新项目驱动因素。  <br/> |
|OptimizerCannotEditDriver = 29404  <br/> |无法编辑项目驱动因素。  <br/> |
|OptimizerCannotCreateMultipleDrivers = 29405  <br/> |无法创建多个驱动因素。  <br/> |
|OptimizerCannotUpdateMultipleDrivers = 29406  <br/> |无法更新多个驱动因素。  <br/> |
|OptimizerInvalidRelativeImportanceValue = 29407  <br/> |相对重要性值无效。  <br/> |
|OptimizerInvalidDriverUid = 29500  <br/> |驱动因素 GUID 无效。  <br/> |
|OptimizerInvalidEntityType = 29501  <br/> |实体类型对优化器无效。  <br/> |
|OptimizerInvalidProjectUid = 29502  <br/> |项目 GUID 无效。  <br/> |
|OptimizerInvalidCustomFieldUid = 29503  <br/> |自定义域 GUID 对优化器无效。  <br/> |
|OptimizerInvalidHardConstraintUid = 29504  <br/> |硬约束 GUID 无效。  <br/> |
|OptimizerInvalidAnalysisUid = 29505  <br/> |分析 GUID 无效。  <br/> |
|OptimizerDriverFilterInvalid = 29506  <br/> |驱动因素筛选器无效。  <br/> |
|OptimizerPrioritizationFilterInvalid = 29507  <br/> |优先顺序筛选器无效。  <br/> |
|OptimizerCannotLoadOptimizationEngine = 29508  <br/> |无法加载优化器计算引擎。  <br/> |
|OptimizerAnalysisFilterInvalid = 29509  <br/> |分析筛选器无效。  <br/> |
|OptimizerSolutionFilterInvalid = 29510  <br/> |优化器的解决方案筛选器无效。  <br/> |
|OptimizerDependenciesFilterInvalid = 29511  <br/> |优化器的依赖关系筛选器无效。  <br/> |
|OptimizerInvalidSolutionUid = 29512  <br/> |优化器的解决方案 GUID 无效。  <br/> |
|OptimizerInvalidViewUid = 29513  <br/> |优化器的视图 GUID 无效。  <br/> |
|OptimizerInvalidAnalysisType = 29600  <br/> |项目组合分析的类型无效。  <br/> |
|OptimizerInvalidPrioritizationType = 29601  <br/> |优化器的优先顺序类型无效。  <br/> |
|OptimizerCannotDeleteAnalysis = 29602  <br/> |无法删除项目组合分析。  <br/> |
|OptimizerCannotCreateAnalysis = 29603  <br/> |无法创建项目组合分析。  <br/> |
|OptimizerCannotUpdateAnalysis = 29604  <br/> |无法更新项目组合分析。  <br/> |
|OptimizerInvalidPrioritizationUid = 29607  <br/> |优先顺序 GUID 无效。  <br/> |
|OptimizerCannotCreateMultipleAnalyses = 29608  <br/> |无法创建多个项目组合分析。  <br/> |
|OptimizerCannotUpdateMultipleAnalyses = 29609  <br/> |无法更新多个项目组合分析。  <br/> |
|OptimizerCannotCalculateProjectPriorities = 29610  <br/> |优化器无法计算项目优先级。  <br/> |
|OptimizerCannotDeleteAnalysisProjectImpact = 29611  <br/> |无法删除项目组合分析中的项目影响。  <br/> |
|OptimizerCannotChangeAnalysisProjects = 29612  <br/> |无法更改项目组合分析中的项目。  <br/> |
|OptimizerCannotChangePriorityData = 29613  <br/> |无法更改优先级数据。  <br/> |
|OptimizerCannotEditAnalysis = 29614  <br/> |无法编辑项目组合分析。  <br/> |
|OptimizerInvalidPlannerData = 29615  <br/> |计划工具数据对优化器无效。  <br/> |
|OptimizerCannotChangeImpactData = 29616  <br/> |无法更改项目影响数据。  <br/> |
|OptimizerInvalidProjectsNumber = 29617  <br/> |项目的数量无效。  <br/> |
|OptimizerCannotAddImpactCFUIDToCFAnalysis = 29618  <br/> |无法为组合分析添加项目影响自定义域 GUID ([PROJECT_IMPACT_CF_UID](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.AnalysisDataSet.AnalysisRow.PROJECT_IMPACT_CF_UID.aspx))。  <br/> |
|OptimizerInvalidDepartmentUid = 29619  <br/> |[DEPARTMENT_UID](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.AnalysisDataSet.AnalysisRow.DEPARTMENT_UID.aspx) 无效。  <br/> |
|OptimizerTooManyProjectsInAnalysis = 29620  <br/> |分析中的项目太多。  <br/> |
|QueueAnalysisCannotDeleteAnalysis = 29680  <br/> |[QueueDeleteAnalyses](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PortfolioAnalyses.QueueDeleteAnalyses.aspx) 方法无法删除分析。  <br/> |
|QueueAnalysisCannotCreateAnalysis = 29681  <br/> |[QueueCreateAnalysis](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PortfolioAnalyses.QueueCreateAnalysis.aspx) 方法无法创建分析。  <br/> |
|QueueAnalysisCannotUpdateAnalysis = 29682  <br/> |[QueueUpdateAnalysis](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PortfolioAnalyses.QueueUpdateAnalysis.aspx) 方法无法更新分析。  <br/> |
|AnalysisMismatchedJobList = 29690  <br/> |未匹配分析作业列表。  <br/> |
|OptimizerInvalidForceInLookupTableUid = 29691  <br/> |无法强制签入查阅表格 GUID。  <br/> |
|OptimizerInvalidForceOutLookupTableUid = 29692  <br/> |无法强制签出查阅表格 GUID。  <br/> |
|OptimizerDuplicateForceLookupTableUids = 29693  <br/> |存在重复的强制查阅表格 GUID。  <br/> |
|OptimizerInvalidDecisionResult = 29701  <br/> |决策结果无效。  <br/> |
|OptimizerInvalidForcedStatus = 29702  <br/> |强制状态无效。  <br/> |
|OptimizerCannotDeleteSolution = 29703  <br/> |[QueueDeleteOptimizerSolutions](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PortfolioAnalyses.QueueDeleteOptimizerSolutions.aspx) 方法无法删除优化器解决方案。  <br/> |
|OptimizerCannotCreateSolution = 29704  <br/> |[QueueCreateOptimizerSolution](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PortfolioAnalyses.QueueCreateOptimizerSolution.aspx) 方法无法创建优化器解决方案。  <br/> |
|OptimizerCannotUpdateSolution = 29705  <br/> |[QueueUpdateAnalysis](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PortfolioAnalyses.QueueUpdateAnalysis.aspx) 方法无法更新优化器解决方案。  <br/> |
|OptimizerCannotCalculateSolutionStrategicAlignment = 29706  <br/> |优化器无法计算用于战略性调整的解决方案。  <br/> |
|OptimizerCannotCreateMultipleSolutions = 29707  <br/> |优化器无法创建多个解决方案。  <br/> |
|OptimizerCannotUpdateMultipleSolutions = 29708  <br/> |优化器无法更新多个解决方案。  <br/> |
|OptimizerCannotAddPrioritizationToCFAnalysis = 29709  <br/> |优化器无法添加要分析的自定义域的优先顺序。  <br/> |
|OptimizerTableIsReadOnly = 29710  <br/> |优化器表为只读。  <br/> |
|OptimizerSolutionCreateMessageFailed = 29711  <br/> |优化器未能生成“解决方案已创建”消息。  <br/> |
|OptimizerSolutionDeleteMessageFailed = 29712  <br/> |优化器未能生成“解决方案已删除”消息。  <br/> |
|OptimizerCannotCalculateEfficientFrontier = 29714  <br/> |优化器无法计算分析的有效边界。  <br/> |
|OptimizerCannotUpdateSolutionProperties = 29715  <br/> |无法更新解决方案属性。  <br/> |
|OptimizerInvalidConstraintPosition = 29716  <br/> |优化器中的约束位置无效。  <br/> |
|OptimizerInvalidHardConstraintPosition = 29717  <br/> |优化器中的硬约束位置无效。  <br/> |
|OptimizerInvalidConstraintLimit = 29718  <br/> |优化器中的约束限制无效。  <br/> |
|OptimizerInvalidConstraintValue = 29719  <br/> |约束值无效。  <br/> |
|OptimizerInvalidSolutionProjectsSet = 29720  <br/> |解决方案中的项目集无效。  <br/> |
|OptimizerCannotCommitSolution = 29721  <br/> |[CommitOptimizerSolution](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PortfolioAnalyses.CommitOptimizerSolution.aspx) 方法无法提交解决方案。  <br/> |
|OptimizerInvalidInputData = 29723  <br/> |优化器的输入数据无效。  <br/> |
|OptimizerInvalidConstraintSet = 29724  <br/> |优化器的约束集无效。  <br/> |
|OptimizerCannotUpdateAnalysisMetrics = 29725  <br/> |无法更新分析指标。  <br/> |
|OptimizerSolutionMismatchedJobList = 29726  <br/> |未匹配解决方案中的作业列表。  <br/> |
|OptimizerInvalidForceLookupTableValue = 29727  <br/> |强制查阅表格值无效。  <br/> |
|OptimizerCannotCreateSolutionWhileAnalysisUpdateIsPending = 29728  <br/> |无法在分析更新挂起时创建优化器解决方案。  <br/> |
|OptimizerProjectSelectorAtLeastOne = 29800  <br/> |必须至少为优化器选择一个项目。  <br/> |
   
表 17 中的错误代码均针对计划工具，它是项目组合分析中使用的组件。

<a name="pj15_ErrorCodes_Planner"></a>

## <a name="table-17-planner-project-portfolio-analysis"></a>表 17. 计划工具（项目组合分析）

|计划工具错误代码|说明|
|:-----|:-----|
|PlannerSolutionMessageDeleteFailed = 28000  <br/> |队列错误：删除计划工具解决方案失败的消息。  <br/> |
|PlannerSolutionMessageCreateFailed = 28001  <br/> |队列错误：创建计划工具解决方案失败的消息。  <br/> |
|PlannerInvalidRBSValueUid = 28002  <br/> |资源细分结构值的 GUID 在计划工具数据中无效。  <br/> |
|PlannerInvalidCustomFieldUid = 28003  <br/> |自定义域的 GUID 无效。  <br/> |
|PlannerHorizonInvalid = 28004  <br/> |计划工具时间范围无效。时间范围是为容量计划指定的时间段。  <br/> |
|PlannerHorizonTooBig = 28005  <br/> |时间范围离现在太遥远。  <br/> |
|PlannerInvalidBookingType = 28006  <br/> |资源预订类型无效。  <br/> |
|PlannerInvalidTimeScale = 28007  <br/> |时间刻度无效。  <br/> |
|PlannerInvalidProjectSNET = 28008  <br/> |项目的“不得早于...开始”日期无效。  <br/> |
|PlannerInvalidProjectFNLT = 28009  <br/> |项目的“不得晚于...完成”日期无效。  <br/> |
|PlannerInvalidAnalysisStartDate = 28010  <br/> |项目的 [START_DATE](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PlannerSolutionDataSet.SolutionProjectRequirementsByRoleRow.START_DATE.aspx) 无效。  <br/> |
|PlannerInvalidAnalysisDuration = 28011  <br/> |[DURATION](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PlannerSolutionDataSet.SolutionProjectsRow.DURATION.aspx) 对组合分析无效。  <br/> |
|PlannerInvalidHorizonStartDate = 28012  <br/> |时间范围的开始日期无效。  <br/> |
|PlannerInvalidHorizonEndDate = 28013  <br/> |时间范围的结束日期无效。  <br/> |
|PlannerInvalidHorizonTimeScale = 28014  <br/> |时间范围的时间刻度无效。  <br/> |
|PlannerInvalidAnalysisType = 28015  <br/> |项目组合分析的类型无效。  <br/> |
|PlannerHorizonStartDateDoesNotMatchTimeScale = 28016  <br/> |时间范围的开始日期与时间刻度不匹配。  <br/> |
|PlannerHorizonEndDateDoesNotMatchTimeScale = 28017  <br/> |时间范围的结束日期与时间刻度不匹配。  <br/> |
|PlannerAnalysisNoCapacityData = 28037  <br/> |项目组合分析没有资源容量数据。  <br/> |
|PlannerInvalidSolutionUid = 28100  <br/> |分析解决方案 GUID 无效。  <br/> |
|PlannerInvalidOptimizerSolutionUid = 28101  <br/> |优化器解决方案 GUID 无效。  <br/> |
|PlannerInvalidLookupTableValueUid = 28102  <br/> |查阅表格值 GUID 无效。  <br/> |
|PlannerInvalidEfficientFrontierUid = 28103  <br/> |[FRONTIER_UID](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PlannerSolutionDataSet.SolutionEfficientFrontierRow.FRONTIER_UID.aspx) 无效.  <br/> |
|PlannerInvalidProjectUid = 28104  <br/> |项目 GUID 无效。  <br/> |
|PlannerInvalidAllocationThreshold = 28105  <br/> |分配阈值无效。  <br/> |
|PlannerInvalidHiringType = 28109  <br/> |[HIRING_TYPE](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PlannerSolutionDataSet.SolutionsRow.HIRING_TYPE.aspx) 无效。 请参阅 [Planner.PlannerHiringType](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.Planner.PlannerHiringType.aspx)。  <br/> |
|PlannerInvalidConstraintType = 28110  <br/> |[CONSTRAINT_TYPE](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PlannerSolutionDataSet.SolutionsRow.CONSTRAINT_TYPE.aspx) 无效。 请参阅 [Planner.ConstraintType](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.Planner.ConstraintType.aspx)。  <br/> |
|PlannerInvalidConstraintValue = 28111  <br/> |[CONSTRAINT_VALUE](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PlannerSolutionDataSet.SolutionsRow.CONSTRAINT_VALUE.aspx) 无效。  <br/> |
|PlannerInvalidRateTable = 28112  <br/> |[RATE_TABLE](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PlannerSolutionDataSet.SolutionsRow.RATE_TABLE.aspx) 无效。  <br/> |
|PlannerInvalidSolutionForConstraint = 28113  <br/> |计划工具解决方案对约束无效。首次传递计划工具期间强制签入的项目太多。  <br/> |
|PlannerInvalidSolutionForDependencies = 28114  <br/> |计划工具解决方案无效，因为要考虑业务依赖关系或冲突的项目太多。此错误在第二次传递时出现。  <br/> |
|PlannerInvalidSolutionForScheduling = 28115  <br/> |计划工具解决方案对计划无效，因为存在循环依赖关系。  <br/> |
|PlannerInvalidAnalysisUid = 28116  <br/> |[ANALYSIS_UID](https://msdn.microsoft.com/library/WebSvcPortfolioAnalyses.PlannerSolutionDataSet.SolutionsRow.ANALYSIS_UID.aspx) 无效。  <br/> |
|PlannerInvalidProjectStartDate = 28200  <br/> |项目开始日期无效。  <br/> |
|PlannerInvalidProjectEndDate = 28201  <br/> |项目结束日期无效。  <br/> |
|PlannerInvalidProjectDuration = 28202  <br/> |项目持续时间无效。  <br/> |
|PlannerInvalidProjectFNLTDate = 28203  <br/> |项目的“不得晚于...完成”日期无效。  <br/> |
|PlannerInvalidProjectSNETDate = 28204  <br/> |项目的“不得早于...开始”日期无效。  <br/> |
|PlannerCannotCreateSolution = 28900  <br/> |计划工具无法创建解决方案。  <br/> |
|PlannerCannotUpdateSolution = 28901  <br/> |计划工具无法更新解决方案。  <br/> |
|PlannerCannotDeleteSolution = 28902  <br/> |计划工具无法删除解决方案。  <br/> |
|PlannerCannotCreateMultipleSolutions = 28903  <br/> |计划工具无法创建多个解决方案。  <br/> |
|PlannerCannotUpdateMultipleSolutions = 28904  <br/> |计划工具无法更新多个解决方案。  <br/> |
|PlannerTableIsReadOnly = 28907  <br/> |**数据表**为只读。  <br/> |
|PlannerCannotCommitSolution = 28908  <br/> |计划工具无法将解决方案提交到数据库。  <br/> |
|PlannerFieldIsReadOnly = 28909  <br/> |域为只读。  <br/> |
|PlannerProjectNotInParentSolution = 28910  <br/> |项目不在父解决方案中。  <br/> |
|PlannerProjectNotSelectedInParentSolution = 28911  <br/> |未在父解决方案中选择项目。  <br/> |
|PlannerProjectNotInParentAnalysis = 28912  <br/> |项目不在父项目组合分析中。  <br/> |
|PlannerProjectBeyondHorizon = 28913  <br/> |项目扩展超出时间范围。  <br/> |
|PlannerResourceAllocationInternalError = 28915  <br/> |资源分配中存在内部错误。  <br/> |
|PlannerResourceAllocationInfeasibleSolution = 28916  <br/> |资源分配是一个不可行的解决方案。  <br/> |
|PlannerProjectEndDateViolatesDependency = 28917  <br/> |项目结束日期违反依赖关系。  <br/> |
|PlannerInvalidProjectsSet = 28919  <br/> |项目集无效。  <br/> |
|PlannerInvalidInputData = 28920  <br/> |计划工具具有无效的输入数据。  <br/> |
|PlannerDecimalOverflowError = 28921  <br/> |计划工具中存在小数溢出错误。  <br/> |
|PlannerSolutionMismatchedJobList = 28922  <br/> |解决方案具有不匹配的作业列表。  <br/> |
|PlannerInvalidForceLookupTableValue = 28923  <br/> |查阅表格的强制值无效。  <br/> |
|PlannerNoHiredResource = 28924  <br/> |不存在针对该建议启用的资源。  <br/> |

<a name="pj15_ErrorCodes_Projects"></a>

## <a name="table-18-project"></a>表 18. 项目

|项目错误代码|说明|
|:-----|:-----|
|ProjectGlobalNotFound = 100  <br/> |无法找到企业全局模板。  <br/> |
|ProjectGlobalCannotBeDeleted = 101  <br/> |无法删除企业全局模板。  <br/> |
|ProjectNotFound = 1000  <br/> |未找到项目。  <br/> |
|ProjectAlreadyExists = 1001  <br/> |项目已存在。  <br/> |
|ProjectCheckedoutToOtherUser = 1002  <br/> |项目已签出给另一用户。  <br/> |
|ProjectTypeInvalidForCreate = 1003  <br/> |创建操作的项目类型无效。  <br/> |
|ProjectParametersInvalid = 1004  <br/> |一个或多个项目参数无效。  <br/> |
|ProjectNotCheckedoutToUser = 1006  <br/> |项目未签出给用户。  <br/> |
|ProjectCheckedout = 1007  <br/> |项目已签出。  <br/> |
|ProjectTypeInvalid = 1008  <br/> |项目类型无效。  <br/> |
|ProjectIDInvalid = 1009  <br/> |项目标识号无效。  <br/> |
|ProjectNameTooLong = 1014  <br/> |项目名称太长。  <br/> |
|ProjectManagerNameTooLong = 1015  <br/> |项目管理者名称太长。  <br/> |
|ProjectNameInvalid = 1016  <br/> |项目名称无效。  <br/> |
|ProjectStartDateMissing = 1025  <br/> |项目开始日期丢失。  <br/> |
|ProjectNameMissing = 1026  <br/> |项目名称丢失。  <br/> |
|ProjectVersionMissing = 1027  <br/> |项目版本丢失。  <br/> |
|ProjectDoesNotExist = 1028  <br/> |项目不存在。  <br/> |
|ProjectMultipleProjectsInvalid = 1029  <br/> |多个项目无效。  <br/> |
|ProjectHasWriteLock = 1030  <br/> |数据库中的项目具有写锁定。  <br/> |
|ProjectHasPendingWriteLock = 1031  <br/> |项目具有挂起的写锁定。  <br/> |
|ProjectHasNoReadLock = 1032  <br/> |项目没有读取锁定。  <br/> |
|ProjectHasReadLock = 1033  <br/> |项目具有读取锁定。  <br/> |
|ProjectNameAlreadyExists = 1034  <br/> |项目名称已存在。  <br/> |
|ProjectOptCriticalSlackLimitInvalid = 1035  <br/> |可选关键宽延时限无效。  <br/> |
|ProjectOptCurrencyPositionInvalid = 1036  <br/> |可选货币位置无效。  <br/> |
|ProjectOptCurrencyDigitsInvalid = 1037  <br/> |可选货币位数无效。  <br/> |
|ProjectOptCurrencySymbolTooLong = 1038  <br/> |可选货币符号太长。  <br/> |
|ProjectCannotDelete = 1039  <br/> |无法删除项目。仅常规或模板服务器端项目可删除。  <br/> |
|ProjectCannotAdd = 1040  <br/> |无法在服务器端项目使用 **AddToProject** 方法。  <br/> |
|ProjectOptCurrencySymbolInvalid = 1041  <br/> |可选货币符号无效。  <br/> |
|ProjectHasNoWriteLock = 1042  <br/> |项目没有写锁定。  <br/> |
|ProjectFilterInvalid = 1043  <br/> |项目筛选器无效。  <br/> |
|ProjectTooLarge = 1044  <br/> |项目建议太大。  <br/> |
|ProjectOptCurrencyCodeNot3Chars = 1045  <br/> |可选货币代码不是三个字符。  <br/> |
|ProjectOptCurrencyCodeInvalid = 1046  <br/> |项目选项中的货币代码无效。  <br/> |
|ProjectActualsAreProtected = 1047  <br/> |项目实际值受保护。  <br/> |
|ProjectTemplateNotFound = 1048  <br/> |未找到项目模板。  <br/> |
|ProjectCurrencyCodeInvalid = 1049  <br/> |货币代码无效。  <br/> |
|ProjectCannotEditCostResource = 1050  <br/> |无法编辑成本资源。  <br/> |
|ProjectIsNotPublished = 1051  <br/> |项目未发布。  <br/> |
|ProjectExceededLWPTaskLimit = 1052  <br/> |超出项目建议（轻型项目）的任务限制。  <br/> |
|ProjectOptFinishDateInvalid = 1053  <br/> |项目选项中的完成日期无效。  <br/> |
|ProjectExceededItemsLimit = 1054  <br/> |超出了要处理的项的限制。Project Server Service 应用程序在所有表中均无法使用 **ProjectDataSet** 添加或更新 1000 个以上的项。若要处理 1000 个以上的项，请使用多个调用，例如，调用 **QueueUpdateProject**。<br/> |
|ProjectColumnNotReadOnly = 1055  <br/> |列为只读。  <br/> |
|ProjectInvalidOwner = 1056  <br/> |项目所有者无效。  <br/> |
|ProjectCantEditPctWrkCompForNonWrkRscs = 1057  <br/> |对于没有实际工作分配的任务，无法编辑 **PctWorkComplete**。  <br/> |
|ProjectCannotEditMaterialResource = 1058  <br/> |无法编辑材料资源。  <br/> |
|ProjectCannotEditFieldWhenTaskHasNoWorkAssignment = 1059  <br/> |无法编辑域，因为任务没有工作分配。  <br/> |
|ProjectSubProjectNotFound = 1070  <br/> |. 未找到任何子项目。  <br/> |
|ProjectResourceNotFound = 1100  <br/> |未找到资源。  <br/> |
|ProjectResourceAlreadyExists = 1101  <br/> |资源已存在。  <br/> |
|ProjectCannotReplaceResourceWithSelf = 1106  <br/> |无法将资源替换为相同对象。  <br/> |
|ProjectCannotChangeLockedTrackingMethod = 1107  <br/> |无法更改，因为跟踪方法已锁定。  <br/> |
|ProjectInvalidColumnForCompatibilityMode = 1108  <br/> |兼容模式的列无效。  <br/> |
|ProjectUpdateInvalidUpdateSequenceNumber = 1151  <br/> |项目更新中的序列号无效。  <br/> |
|ProjectUpdateDuplicateUpdateSequenceNumber = 1152  <br/> |项目更新中的序列号重复。  <br/> |
|ProjectUpdateNullUpdateSequenceNumber = 1153  <br/> |项目更新中的序列号为 Null。  <br/> |
|ProjectUpdateNullUpdateColumnNames = 1154  <br/> |项目更新中的列名称为 Null。  <br/> |
|ProjectUpdateInvalidProjectUID = 1155  <br/> |项目更新中的项目 GUID 无效。  <br/> |
|ProjectUpdateInvalidColumnForUpdate = 1156  <br/> |列对项目更新无效。  <br/> |
|ProjectUpdateCannotEditColumn = 1157  <br/> |无法编辑项目更新中的列。  <br/> |
|ProjectUpdateNoChangesToValidateAndSchedule = 1158  <br/> |项目更新未包含任何已验证和已计划的更改。  <br/> |
|LinkNotFound = 1159  <br/> |未找到链接。  <br/> |
|ProjectUpdateInvalidColumnValue = 1160  <br/> |项目更新中的列值无效。  <br/> |
|ProjectCannotDeleteItem = 1161  <br/> |无法删除项目项。  <br/> |
|ProjectUpdateCannotComputeOptIndex = 1162  <br/> |无法计算项目更新中的优化索引。  <br/> |
|ProjectCannotUpdateDueToVisibilityMode = 1163  <br/> |无法更新，因为项目处于可见性模式。  <br/> |
|ProjectNodeConsistencyException = 9132  <br/> |异常：节点不一致。  <br/> |
|ProjectSchedulingEngineException = 9133  <br/> |计划引擎中存在异常。  <br/> |
|ProjectFormulaCalculationException = 9134  <br/> |公式计算中存在异常。  <br/> |
|ProjectUpdateDatabaseException = 9135  <br/> |数据库更新中存在异常。  <br/> |
|ProjectDeleteException = 9136  <br/> |删除项目时出现异常。  <br/> |
|ProjectOperationException = 9137  <br/> |项目操作中存在异常。  <br/> |
|ProjectCannotComunicateWithPCS = 9138  <br/> |未能与 PCS 工作进程通信。  <br/> |
|ProjectPCSSessionInvalid = 9139  <br/> |引擎会话中的项目未能打开。  <br/> |
|ProjectPublishFailure = 23000  <br/> |发布项目时队列中出现故障。  <br/> |
|ProjectCurrencyConflict = 23001  <br/> |指定货币中存在冲突。  <br/> |
|ProjectPublishFailed = 23002  <br/> |排队时发布项目失败。  <br/> |
|ProjectReversePublishFailed = 23003  <br/> |项目发布操作在排队时失败。  <br/> |
|ProjectReversePublishFailure = 23004  <br/> |队列处理过程中反向项目发布失败。  <br/> |
|ProjectArchiveRetentionDeleteFailure = 23005  <br/> |由于存档保留，删除项目时失败。  <br/> |
|ProjectDeleteFailure = 23006  <br/> |删除项目时失败。  <br/> |
|ProjectPublishEnqueueFailure = 23007  <br/> |排队时发布项目失败。  <br/> |
|ProjectCheckinFailure = 23008  <br/> |队列处理过程中签入项目失败。  <br/> |
|ProjectCheckinFailed = 23009  <br/> |排队时签入项目失败。  <br/> |
|ProjectCheckoutFailed = 23010  <br/> |用户没有项目签出权限。  <br/> |
|ProjectPublishSummaryEnqueueFailure = 23011  <br/> |排队时发布摘要失败。  <br/> |
|ProjectPublishSummaryFailed = 23012  <br/> |发布摘要失败。  <br/> |
|ProjectUpdateScheduledProjectFailure = 26026  <br/> |队列处理过程中项目计划更新失败。  <br/> |
|ProjectSyncProjectEnterpriseEntitiesFailure = 26033  <br/> |队列处理过程中同步项目企业实体失败。  <br/> |
|GeneralDalDatabaseIsReadOnly = 26034  <br/> |项目明细加载失败。数据库为只读。  <br/> |
|GeneralDatabaseCommunicationError = 26035  <br/> |可能有许多不同的原因，例如网络或身份验证问题。  <br/> |

<a name="pj15_ErrorCodes_RDS"></a>

## <a name="table-19-reporting-data-service-rds"></a>表 19. 报告数据服务 (RDS)

|RDS 错误代码|说明|
|:-----|:-----|
|ReportingAttributeCubeSettingsChangedMessageFailed = 24000  <br/> |RDS 更改消息由于某个多维数据集设置属性失败。  <br/> |
|ReportingBaseCalendarChangeMessageFailed = 24001  <br/> |RDS 更改消息由于基准日历失败。  <br/> |
|ReportingCustomFieldMetadataChangeMessageFailed = 24002  <br/> |RDS 更改消息由于自定义域元数据失败。  <br/> |
|ReportingEntityUserViewChangedMessageFailed = 24003  <br/> |RDS 更改消息由于实体用户视图失败。  <br/> |
|ReportingFiscalPeriodChangeMessageFailed = 24004  <br/> |RDS 更改消息由于财务期间失败。  <br/> |
|ReportingLookupTableChangeMessageFailed = 24005  <br/> |RDS 更改消息由于查阅表格失败。  <br/> |
|ReportingProjectChangeMessageFailed = 24006  <br/> |RDS 更改消息由于项目失败。  <br/> |
|ReportingResourceCapacityUpdateMessageFailed = 24007  <br/> |RDS 更新消息由于资源容量失败。  <br/> |
|ReportingResourceChangeMessageFailed = 24008  <br/> |RDS 更改消息由于资源失败。  <br/> |
|ReportingTimesheetAdjustMessageFailed = 24009  <br/> |RDS 调整消息由于时间表失败。  <br/> |
|ReportingTimesheetClassCreateMessageFailed = 24010  <br/> |RDS 创建消息由于时间表类失败。  <br/> |
|ReportingTimesheetDeleteMessageFailed = 24011  <br/> |RDS 删除消息由于时间表失败。  <br/> |
|ReportingTimesheetPeriodDeleteMessageFailed = 24012  <br/> |RDS 删除消息由于时间表期间失败。  <br/> |
|ReportingTimesheetPeriodMessageFailed = 24013  <br/> |RDS 消息由于时间表期间失败。  <br/> |
|ReportingTimesheetSaveMessageFailed = 24014  <br/> |RDS 保存消息由于时间表失败。  <br/> |
|ReportingTimesheetStatusChangeMessageFailed = 24015  <br/> |RDS 更改消息由于时间表状态失败。  <br/> |
|ReportingWSSSyncMessageFailed = 24016  <br/> |RDS 消息由于 SharePoint 同步失败。  <br/> |
|ReportingGetSPWebFailed = 24017  <br/> |RDS 未能获取 SharePoint Web 值。  <br/> |
|ReportingWssSyncListFailed = 24018  <br/> |RDS 未能与 SharePoint 列表同步。  <br/> |
|ReportingWssTransferLinksFailed = 24019  <br/> |RDS 未能传输 SharePoint 链接。  <br/> |
|ReportingQueueMessageSubmitFailed = 24020  <br/> |RDS 未能将消息提交到队列。  <br/> |
|ReportingWssSyncHRefFailed = 24021  <br/> |RDS 未能与 SharePoint HRef 值同步。  <br/> |
|ReportingSyncGlobalDataMessageFailed = 24022  <br/> |与企业全局数据同步的 RDS 消息失败。  <br/> |
|ReportingRDBRefreshMessageFailed = 24023  <br/> |刷新 RDB 的 RDS 消息失败。  <br/> |
|ReportingAttributeCubeDepartmentsChangedMessageFailed = 24024  <br/> |RDS 消息未能更改 OLAP 多维数据集的部门属性。  <br/> |
|ReportingTimesheetProjectAggregationMessageFailed = 24025  <br/> |RDS 消息未能聚合 RDB 中时间表的项目。  <br/> |
|ReportingRdbBulkDataSyncMessageFailed = 24026  <br/> |RDS 消息由于 RDB 中的批量数据同步失败。  <br/> |
|ReportingWorkflowMetadataSyncMessageFailed = 24027  <br/> |RDS 消息未能同步工作流元数据。  <br/> |
|ReportingProjectWorkflowInformationSyncMessageFailed = 24028  <br/> |RDS 消息未能同步项目工作流信息。  <br/> |
|ReportingEptSyncMessageFailed = 24029  <br/> |RDS 消息未能同步企业项目模板。  <br/> |
|ReportingSummaryProjectPublishMessageFailed = 24030  <br/> |RDS 消息未能发布摘要项目。  <br/> |
|ReportingSolutionCommitedDecisionChangedMessageFailed = 24031  <br/> |RDS 消息未能更改解决方案的已提交决策。  <br/> |
|ReportingDelayedUpgradeFailed = 24032  <br/> |RDB 延迟升级失败。  <br/> |

<a name="pj15_ErrorCodes_Resources"></a>

## <a name="table-20-resource"></a>表 20. 资源

|资源错误代码|说明|
|:-----|:-----|
|ResourceNotFound = 2000  <br/> |未找到资源。  <br/> |
|ResourceAlreadyExists = 2001  <br/> |资源已存在。  <br/> |
|ResourceCheckedoutToOtherUser = 2002  <br/> |资源已签出给另一用户。  <br/> |
|ResourceUIDInvalid = 2011  <br/> |资源 GUID 无效。  <br/> |
|ResourceNameInvalid = 2016  <br/> |资源名称无效。  <br/> |
|ResourceNameTooLong = 2017  <br/> |资源名称太长。  <br/> |
|ResourceInitialsTooLong = 2018  <br/> |资源缩写太长。  <br/> |
|ResourceCheckedout = 2025  <br/> |资源已签出。  <br/> |
|ResourceNTAccountInvalid = 2026  <br/> |资源 Windows (NTLM) 帐户无效。  <br/> |
|ResourceNameAlreadyInUse = 2027  <br/> |资源名称已被使用。名称必须是唯一的。  <br/> |
|ResourceNTAccountAlreadyInUse = 2028  <br/> |资源 NTLM 帐户已被使用。  <br/> |
|ResourceAdGuidAlreadyInUse = 2029  <br/> |资源 GUID 已被使用。  <br/> |
|ResourceHasActuals = 2031  <br/> |资源具有实际值。  <br/> |
|ResourceNTAccountTooLong = 2035  <br/> |NTLM 帐户太长。  <br/> |
|ResourceEMailAddressTooLong = 2036  <br/> |资源电子邮件地址太长。  <br/> |
|ResourceCodeTooLong = 2037  <br/> |资源代码太长。  <br/> |
|ResourceGroupTooLong = 2038  <br/> |资源组太长。  <br/> |
|ResourceWorkGroupInvalid = 2039  <br/> |资源工作组无效。  <br/> |
|ResourceTypeInvalid = 2040  <br/> |资源类型无效。  <br/> |
|ResourceNonWorkResourceWithEMailInvalid = 2044  <br/> |非工作资源不能具有电子邮件地址。  <br/> |
|rsResourceNameHasTrailingOrLeadingWhitespace = 2046  <br/> |资源名称具有前导或尾随空格。  <br/> |
|ResourceCannotDeleteCallingUserAccount = 2047  <br/> |用户不能删除其自己的帐户。  <br/> |
|ResourceInitialsInvalid = 2048  <br/> |资源缩写无效。  <br/> |
|ResourceAccrueAtInvalid = 2049  <br/> |实际值无效。  <br/> |
|ResourceNonMaterialResourceCannotHaveMaterialLabel = 2050  <br/> |非材料资源不能具有材料标签。  <br/> |
|ResourceMaterialResourceCannotHaveCertainFields = 2051  <br/> |材料资源不能包含某些域。  <br/> |
|ResourceAvailFromAvailToOverlap = 2052  <br/> |可用的开始日期和可用的结束日期重叠。  <br/> |
|ResourceInvalidEmailLanguage = 2053  <br/> |电子邮件语言无效。  <br/> |
|ResourceBookingTypeInvalid = 2055  <br/> |预订类型无效。  <br/> |
|ResourceCannotReplaceMaterialResourceWithNonMaterialResource = 2056  <br/> |无法将材料资源替换为非材料资源。  <br/> |
|ResourceCannotUpdateEnterpriseResource = 2057  <br/> |无法更新企业资源。  <br/> |
|rsResourceCannotAddLocalWithSameNameAsEnterprise = 2058  <br/> |无法添加使用的名称与企业资源相同的本地资源。  <br/> |
|ResourceCannotSetRateOnCostResource = 2059  <br/> |无法对成本资源设置费率。  <br/> |
|ResourceCannotSetRateOnMaterialResource = 2060  <br/> |无法对材料资源设置费率。  <br/> |
|ResourceCannotSetCanLevelOnNonWorkResource = 2061  <br/> |无法对非工作资源设置级别。  <br/> |
|ResourceCannotDeleteThisUser = 2062  <br/> |无法删除此用户。  <br/> |
|ResourceCannotDeactivateSelf = 2063  <br/> |资源不能停用自身。  <br/> |
|ResourceAvailabilityDateRangesOverlap = 2064  <br/> |资源可用性日期范围重叠。  <br/> |
|ResourceAvailabilityOutsideTheHireAndTerminationDateRange = 2065  <br/> |资源可用性日期位于启用和终止日期范围之外。  <br/> |
|ResourceFilterInvalid = 2066  <br/> |资源的筛选器无效。  <br/> |
|ResourceSegmentWithThisEffectiveDateDoesNotExist = 2067  <br/> |不能删除尚未保存的资源费率。  <br/> |
|ResourceSegmentWithThisEffectiveDateAlready = 2068  <br/> |具有此生效日期的段已存在。  <br/> |
|ResourceUserHasItemCheckedOutToItStill = 2069  <br/> |用户仍签出有某个项。  <br/> |
|ResourceInvalidHireDate = 2070  <br/> |启用日期无效。  <br/> |
|ResourceInvalidTerminationDate = 2071  <br/> |终止日期无效。  <br/> |
|ResourceCannotChangeExistingResourceType = 2072  <br/> |无法更改资源类型。  <br/> |
|ResourceCannotSetTimesheetManagerOnSpecifiedResource = 2073  <br/> |无法对指定资源设置时间表管理者。  <br/> |
|ResourceInvalidTimesheetManager = 2074  <br/> |时间表管理者无效。  <br/> |
|ResourceInvalidAssignmentOwner = 2075  <br/> |工作分配所有者无效。  <br/> |
|ResourceCannotCreateCostResource = 2076  <br/> |无法创建成本资源。  <br/> |
|ResourceInvalidRbsValue = 2077  <br/> |RBS 值无效。  <br/> |
|ResourceCannotSetAssignmentOwnerOnSpecifiedResource = 2078  <br/> |无法对指定资源设置工作分配所有者。  <br/> |
|ResourceFieldsInvalidForBudget = 2079  <br/> |预算的一个或多个域无效。  <br/> |
|ResourceHyperlinkInvalid = 2080  <br/> |资源超链接无效。  <br/> |
|ResourceAuthorizationValidOnlyOnWorkResources = 2081  <br/> |授权仅对工作资源有效。  <br/> |
|ResourceIsProjectOwner = 2082  <br/> |无法删除资源，因为资源是项目所有者。  <br/> |
|ResourceIsTimesheetManager = 2083  <br/> |无法删除资源，因为资源是时间表管理者。  <br/> |
|ResourceIsDefaultAssignmentOwner = 2084  <br/> |无法删除资源，因为资源是默认工作分配所有者。  <br/> |
|ResourceIsAssignmentOwner = 2085  <br/> |无法删除资源，因为资源是工作分配所有者。  <br/> |
|ResourceIsUsedInResourcePlan = 2086  <br/> |无法删除资源，因为将在资源计划中使用资源。  <br/> |
|ResourceCannotDeleteEnterpriseResource = 2087  <br/> |由于未知原因，无法删除企业资源。  <br/> |
|ResourceSetResourceAuthorizationFailed = 2088  <br/> |未能设置资源授权。  <br/> |
|ResourceTooManyResourcesSpecifiedToDelete = 2089  <br/> |无法删除指定数量的资源。  <br/> |
|ResourceTooManyResourcesReturned = 2090  <br/> |方法无法处理此数量的资源。  <br/> |
|ResourceCannotDeleteWorkflowProxyUser = 2091  <br/> |无法删除工作流代理用户。  <br/> |
|ResourceInvalidEmailWithExchangeSync = 2092  <br/> |电子邮件对与 Microsoft Exchange Server 的同步无效。  <br/> |
|ResourceInvalidResourceTypeWithExchangeSync = 2093  <br/> |资源类型对与 Exchange Server 的同步无效。  <br/> |
|ResourceInvalidPrincipalNameWithExchangeSync = 2094  <br/> |资源主体名称对与 Exchange Server 的同步无效。  <br/> |
|ResourceInvalidAuthenticationTypeWithExchangeSync = 2095  <br/> |资源身份验证类型对与 Exchange Server 的同步无效。  <br/> |
|ResourceExchangeSyncFlagAndPrincipalNameMismatch = 2096  <br/> |Exchange Server 同步标志与资源的主体名称不匹配。  <br/> |
|ResourceUnsupportedUserUpdateInSharePointSecurityMode = 2097  <br/> |在 SharePoint 安全模式中不支持用户创建。  <br/> |

<a name="pj15_ErrorCodes_ResourcePlans"></a>

## <a name="table-21-resource-plan"></a>表 21. 资源计划

|资源计划错误代码|说明|
|:-----|:-----|
|ResourcePlanProjectPublishIncomplete = 30000  <br/> |资源计划的项目发布未完成。  <br/> |
|ResourcePlanInvalidResourceType = 30001  <br/> |资源计划中的资源类型无效。  <br/> |
|ResourcePlanInactiveResourcesDisallowed = 30002  <br/> |项目计划中不允许使用无效资源。  <br/> |
|ResourcePlanFilterInvalid = 30003  <br/> |资源计划筛选器无效。  <br/> |
|ResourcePlanSaveFailure = 30004  <br/> |未能保存资源计划。  <br/> |
|ResourcePlanCheckinFailure = 30005  <br/> |未能签入资源计划。  <br/> |
|ResourcePlanDeleteFailure = 30006  <br/> |未能删除资源计划。  <br/> |
|ResourcePlanInvalidUtilizationType = 30007  <br/> |资源计划利用率类型无效。  <br/> |
|ResourcePlanInvalidTimescale = 30008  <br/> |资源计划时间刻度无效。  <br/> |
|ResourcePlanMismatchedJobList = 30009  <br/> |资源计划作业列表中存在不匹配项。  <br/> |
|ResourcePlanAlreadyExists = 30010  <br/> |资源计划已存在。  <br/> |
|ResourcePlanInvalidProjectUID = 30011  <br/> |资源计划的项目 GUID 无效。  <br/> |
|ResourcePlanResourceAlreadyExists = 30012  <br/> |资源已存在于资源计划中。  <br/> |
   
表 22 中的错误代码是 **PWA** Web 服务中 **Rules** 方法的错误代码。这些代码供内部使用。 

<a name="pj15_ErrorCodes_Rules"></a>

## <a name="table-22-rules"></a>表 22. 规则

|规则错误代码|说明|
|:-----|:-----|
|RulesNameTooLong = 21001  <br/> |批准规则的名称太长。 仅供 Project Web App 内部使用。  <br/> |
|RulesDescriptionTooLong = 21002  <br/> |规则说明太长。 仅供 Project Web App 内部使用。  <br/> |
|RulesInvalidRuleType = 21003  <br/> |规则类型无效。 仅供 Project Web App 内部使用。  <br/> |
|RulesInvalidConditionType = 21004  <br/> |规则的条件类型无效。 仅供 Project Web App 内部使用。  <br/> |
|RulesInvalidOperatorType = 21005  <br/> |规则的运算符类型无效。 仅供 Project Web App 内部使用。  <br/> |
|RulesInvalidListItemType = 21007  <br/> |规则的列表项类型无效。 仅供 Project Web App 内部使用。  <br/> |
|RulesNameInvalidCharacters = 21008  <br/> |规则名称中存在一个或多个无效的字符。 仅供 Project Web App 内部使用。  <br/> |
|RulesDescriptionInvalidCharacters = 21009  <br/> |规则说明中存在一个或多个无效的字符。 仅供 Project Web App 内部使用。  <br/> |
|RulesInvalidValueType = 21010  <br/> |规则中的值类型无效。 仅供 Project Web App 内部使用。  <br/> |

<a name="pj15_ErrorCodes_Security"></a>

## <a name="table-23-security"></a>表 23. 安全性

|安全错误代码|说明|
|:-----|:-----|
|SecurityGroupCouldNotBeCreated = 19001  <br/> |无法创建安全组。  <br/> |
|SecurityFieldAccessIDInvalid = 19003  <br/> |安全域访问代码标识号无效。  <br/> |
|SecurityCannotUpdateFacForNonExistentCategory = 19004  <br/> |安全类别不存在；无法更新域访问代码。  <br/> |
|SecurityDuplicateCategoryUid = 19005  <br/> |安全类别 GUID 重复。  <br/> |
|SecurityDuplicateGroupUid = 19006  <br/> |安全组 GUID 重复。  <br/> |
|SecurityDuplicateTemplateUid = 19007  <br/> |安全模板 GUID 重复。  <br/> |
|SecurityInvalidTemplateUidRef = 19008  <br/> |安全模板 GUID 无效。  <br/> |
|SecurityInvalidGlobalPermission = 19009  <br/> |全局安全权限无效。  <br/> |
|SecurityInvalidCategoryPermission = 19010  <br/> |安全类别权限无效。  <br/> |
|SecurityUpdatedGroupNotFound = 19013  <br/> |未找到已更新的安全组。  <br/> |
|SecurityUpdatedCategoryNotFound = 19014  <br/> |未找到已更新的安全类别。  <br/> |
|SecurityUpdatedTemplateNotFound = 19015  <br/> |未找到已更新的安全模板。  <br/> |
|SecurityGroupMemberNotFound = 19016  <br/> |未找到安全组成员。  <br/> |
|SecurityUserNotFound = 19018  <br/> |未找到 Project Server 用户。  <br/> |
|SecurityNoCategoryRelationForPermission = 19019  <br/> |未为权限找到安全类别关系。  <br/> |
|SecurityCannotDeleteDefaultGroup = 19020  <br/> |无法删除默认安全组。  <br/> |
|SecurityCannotDeleteDefaultCategory = 19021  <br/> |无法删除默认安全类别。  <br/> |
|SecurityCategoryCouldNotBeCreated = 19022  <br/> |无法创建安全类别。  <br/> |
|SecurityNoCategoryForPermission = 19023  <br/> |未为权限找到安全类别。  <br/> |
|SecurityNoCategoryForObject = 19024  <br/> |未为对象找到安全类别。  <br/> |
|SecurityNoCategoryForRule = 19025  <br/> |未为用户找到安全类别。  <br/> |
|SecurityNoGroupForPermission = 19026  <br/> |未为权限找到安全组。  <br/> |
|SecurityCannotSetPermissionForFieldGroup = 19027  <br/> |无法设置安全组域的权限。  <br/> |
|SecurityInvalidFieldGroup = 19028  <br/> |安全组域无效。  <br/> |
|SecurityCannotSetOrgPermission = 19029  <br/> |无法设置安全组织权限。  <br/> |
|SecurityInvalidOrgPermission = 19030  <br/> |安全组织权限无效。  <br/> |
|SecurityInvalidSecurityRule = 19031  <br/> |安全规则无效。  <br/> |
|SecurityTemplateNotFound = 19034  <br/> |未找到安全模板。  <br/> |
|SecurityInvalidObjectType = 19035  <br/> |安全对象类型无效。  <br/> |
|SecurityDuplicateUid = 19036  <br/> |安全对象 GUID 重复。  <br/> |
|SecurityObjectNotFound = 19037  <br/> |未找到安全对象。  <br/> |
|SecurityInvalidCategoryUidRef = 19080  <br/> |安全类别 GUID 无效。  <br/> |
|SecurityInvalidProjectUidRef = 19081  <br/> |安全对象的项目 GUID 无效。  <br/> |
|SecurityInvalidGroupUidRef = 19082  <br/> |安全组 GUID 无效。  <br/> |
|SecurityInvalidUserUidRef = 19083  <br/> |安全对象的用户 GUID 无效。  <br/> |
|SecurityInvalidCategoryPermissionUidRef = 19084  <br/> |安全类别的权限 GUID 无效。  <br/> |
|SecurityInvalidGlobalPermissionUidRef = 19085  <br/> |安全全局权限 GUID 无效。  <br/> |
|SecurityInvalidResourceUidRef = 19086  <br/> |安全对象的资源 GUID 无效。  <br/> |
|SecurityDeleteNotSupportedBySetMethod = 19087  <br/> |方法无法删除安全对象。  <br/> |
|SecurityInvalidProjectCategoryPermissionUidRef = 19088  <br/> |项目类别权限 GUID 无效。  <br/> |
|SecurityCannotModifyCoreProjectCategoryDataInUpdate = 19089  <br/> |安全更新方法无法修改核心项目类别数据。  <br/> |
|SecurityProjectCategoryEntitiesDoNotAllowInPlaceChanges = 19090  <br/> |安全类别实体在更新中无法更改。  <br/> |
|SecurityCategoryCannotAddRelationForDeletedCategory = 19091  <br/> |无法为已删除安全类别添加关系。  <br/> |
|SecurityCategoryCannotAddPermissionForDeletedCategory = 19092  <br/> |无法为已删除安全类别添加权限。  <br/> |
|SecurityCategoryCannotAddPermissionForDeletedRelation = 19093  <br/> |无法为已删除安全类别关系添加权限。  <br/> |
|SecurityCategoryCannotDeleteRelationForNewlyAddedCategory = 19094  <br/> |无法删除新添加的安全类别的关系。  <br/> |
|SecurityCategoryCannotDeletePermissionForNewlyAddedCategory = 19095  <br/> |无法删除新添加的安全类别的权限。  <br/> |
|SecurityCategoryCannotDeletePermissionForNewlyAddedRelation = 19096  <br/> |无法删除安全类别中新添加的关系的权限。  <br/> |
|SecurityCategoryCannotHaveDuplicateUserOrGroupUidsForRelation = 19097  <br/> |安全类别关系不能具有重复的用户或组 UID。  <br/> |
|SecurityCategoryPermissionMustHaveMatchingRelation = 19098  <br/> |类别权限必须具有匹配的安全类别关系。  <br/> |
|SecurityCategoryProjectAlreadyHasSecurityProjectCategory = 19099  <br/> |所选类别列表已具有项目安全类别。  <br/> |

<a name="pj15_ErrorCodes_Events"></a>

## <a name="table-24-project-server-event"></a>表 24. Project Server 事件

|Project Server 事件错误代码|说明|
|:-----|:-----|
|ServerEventInvalidEventId = 19033  <br/> |Project Server 事件标识号无效。  <br/> |
|ServerEventServiceNotFound = 22003  <br/> |未找到 Project Server 事件服务。此错误未在 Project Server 代码中使用，但它将映射到原始统一日志记录服务 (ULS) 事件中。  <br/> |
|ServerEventRemoteCouldNotReachProxy = 22005  <br/> |远程 Project Web App 无法到达代理 Project Server 事件管理器。 此错误不在 Project Server 代码中使用，但它将映射到原始 ULS 事件。  <br/> |
|ServerEventManagerCouldNotReachRemote = 22006  <br/> |Project Server 事件管理器无法到达远程 Project Web App。 此错误不在 Project Server 代码中使用，但它将映射到原始 ULS 事件。  <br/> |
|ServerEventHandlerNotSigned = 22007  <br/> |Project Server 事件处理程序未签名。  <br/> |
|ServerEventHandlerMalformedAssemblyName = 22008  <br/> |Project Server 事件处理程序的程序集名称无效。  <br/> |
|ServerEventHandlerOrderInvalid = 22009  <br/> |Project Server 事件处理程序的顺序无效。  <br/> |
|ServerEventHandlerDuplicateEntry = 22010  <br/> |Project Server 事件处理程序的条目重复。  <br/> |
|ServerEventHandlerNotFound = 22011  <br/> |未找到 Project Server 事件处理程序。  <br/> |
|ServerEventHandlerDuplicateName = 22012  <br/> |Project Server 事件处理程序的名称重复。  <br/> |
|ServerEventHandlerNullAssemblyNameAndEndpointUrl = 22013  <br/> |验证是否存在终结点 URL 或程序集名称。  <br/> |

<a name="pj15_ErrorCodes_Statusing"></a>

## <a name="table-25-statusing-web-service"></a>表 25. 状态 Web 服务 

|状态 Web 服务错误代码|说明|
|:-----|:-----|
|StatusingInvalidEntity = 3102  <br/> |**状态**的实体无效。  <br/> |
|StatusingGetDataForTaskFailed = 3103  <br/> |未能获取任务状态数据。  <br/> |
|StatusingGetTaskOrAssnCntrFailed = 3104  <br/> |未能获取任务或工作分配中心的状态。  <br/> |
|StatusingInvalidPIDForProjCntr = 3105  <br/> |项目中心的 **Statusing** 属性标识号无效。  <br/> |
|StatusingDeleteAssnFailed = 3106  <br/> |无法删除**状态**进程中的工作分配。  <br/> |
|StatusingAssnSaveFailed = 3107  <br/> |无法保存**状态**进程中的工作分配。  <br/> |
|StatusingTaskSaveFailed = 3108  <br/> |无法保存**状态**进程中的任务。  <br/> |
|StatusingInvalidPID = 3109  <br/> |**Statusing** 属性标识号无效。  <br/> |
|StatusingSetDataValueInvalid = 3111  <br/> |**状态**数据值无效。  <br/> |
|StatusingSetDataFailed = 3112  <br/> |无法设置**状态**数据值。  <br/> |
|StatusingInvalidDelegationStart = 3113  <br/> |**DelegateAssignments** 方法中的工作分配开始时间无效。  <br/> |
|StatusingApprovalUpdateFailed = 3114  <br/> |未能更新状态审批。  <br/> |
|StatusingInvalidApprovalType = 3115  <br/> |状态审批类型无效。  <br/> |
|StatusingInternalError = 3116  <br/> |**Statusing** 方法中的内部处理错误。  <br/> |
|StatusingInvalidUpdateData = 3117  <br/> |**Statusing** 方法中的更新数据无效。  <br/> |
|StatusingProjectUpdateFailed = 3118  <br/> |项目的**状态**更新失败。  <br/> |
|StatusingInvalidPreviewData = 3119  <br/> |**状态**预览数据无效。  <br/> |
|StatusingInvalidTransaction = 3120  <br/> |**状态**事务无效。  <br/> |
|StatusingTooManyResults = 3121  <br/> |结果太多。读取时间分段状态数据时，将返回 5000 以上的行。  <br/> |
|StatusingInvalidInterval = 3122  <br/> |**Statusing** 方法中的间隔无效。间隔必须以分钟为单位，并且必须大于零。<br/> |
|StatusingApplyUpdatesFailed = 3123  <br/> |将请求进行排队时无法应用**状态**更新。  <br/> |
|StatusingApplyUpdatesFailure = 3124  <br/> |在队列处理期间无法应用**状态**更新。  <br/> |
|StatusingInvalidWorkData = 3125  <br/> |**状态**的工作数据无效。  <br/> |
|StatusingMissingNameAttribute = 3126  <br/> |缺少**状态**的名称属性。  <br/> |
|StatusingInvalidNameAttribute = 3127  <br/> |**状态**的名称属性无效。  <br/> |
|StatusingInvalidData = 3128  <br/> |**状态**数据无效。  <br/> |
|StatusingInvalidChangelist = 3130  <br/> |**UpdateStatus** 方法的 _changexml_ 参数中的 XML 数据无效。  <br/> |
|StatusingInsufficientAssignmentRights = 3131  <br/> |**SetAssignmentWorkData** 无法更新工作分配，因为用户没有权限。  <br/> |
|StatusingInvalidChangeNumber = 3132  <br/> |**状态**更改编号无效。  <br/> |
|StatusingPidNotEditable = 3133  <br/> |**Statusing** 属性标识号不可编辑。  <br/> |
|StatusingCannotSetTimephasedDataInManualTasks = 3134  <br/> |无法在**状态**的手动任务中设置时间分段数据。  <br/> |
|StatusingCannotChangeTaskMode = 3135  <br/> |无法更改**状态**的任务模式。  <br/> |
   
表 26 中的错误代码是 **PWA** Web 服务中 **StatusReports** 方法的错误代码。 这些代码供 Project Web App 内部使用。 

<a name="pj15_ErrorCodes_StatusReports"></a>

## <a name="table-26-statusreports"></a>表 26. 状态报告 

|状态报告错误代码|说明|
|:-----|:-----|
|StatusReportsUnknownError = 12100  <br/> |**状态报告**中的未知错误。  <br/> |
|StatusReportsPeriodUnmatched = 12101  <br/> |无法匹配状态报告期间。  <br/> |
|StatusReportsPeriodUnavailable = 12102  <br/> |状态报告期间不可用。  <br/> |
|StatusReportsInvalidFormInput = 12103  <br/> |状态报告表单中的数据无效。  <br/> |

<a name="pj15_ErrorCodes_Tasks"></a>

## <a name="table-27-task"></a>表 27. 任务 

|任务错误代码|说明|
|:-----|:-----|
|TaskIDInvalid = 7001  <br/> |任务 GUID 无效。  <br/> |
|TaskNameTooLong = 7003  <br/> |任务名称太长。  <br/> |
|TaskTypeInvalid = 7005  <br/> |任务类型无效。  <br/> |
|TaskPriorityInvalid = 7006  <br/> |任务优先级无效。  <br/> |
|TaskConstraintTypeInvalid = 7007  <br/> |任务约束类型无效。  <br/> |
|TaskNameInvalid = 7008  <br/> |任务名称无效。  <br/> |
|TaskConstraintTypeRequiresConstraint = 7010  <br/> |任务需要约束类型。  <br/> |
|TaskConstraintTypeCannotHaveConstraintDate = 7011  <br/> |无法具有约束类型的约束日期。  <br/> |
|TaskSummaryTaskCannotBeMilestone = 7013  <br/> |摘要任务不能是里程碑。  <br/> |
|TaskFixedCostAccrualInvalid = 7014  <br/> |任务的固定成本实际值无效。  <br/> |
|TaskPercentCompleteInvalid = 7015  <br/> |任务的完成百分比值无效。  <br/> |
|TaskWorkPercentCompleteInvalid = 7016  <br/> |任务工作的完成百分比值无效。  <br/> |
|TaskPhysicalPercentCompleteInvalid = 7017  <br/> |任务实际的完成百分比值无效。  <br/> |
|TaskLinkTypeInvalid = 7018  <br/> |任务链接类型无效。  <br/> |
|TaskAlreadyExists = 7019  <br/> |任务已存在。  <br/> |
|TaskLinkAlreadyExists = 7020  <br/> |任务链接已存在。  <br/> |
|TaskNotFound = 7021  <br/> |未找到任务。  <br/> |
|TaskLinkNotFound = 7022  <br/> |未找到任务链接。  <br/> |
|TaskLinkLagInvalid = 7023  <br/> |任务链接的延搁时间无效。  <br/> |
|TaskUnableToInsert = 7025  <br/> |无法插入任务。  <br/> |
|TaskAddPositionInvalid = 7026  <br/> |任务的添加位置无效。  <br/> |
|TaskOutlineLevelInvalid = 7027  <br/> |任务大纲级别无效。  <br/> |
|TaskDurationFormatInvalid = 7028  <br/> |任务持续时间格式无效。  <br/> |
|TaskCannotAddWhereSpecified = 7029  <br/> |无法在指定位置添加任务。  <br/> |
|TaskEarnedValueMethodInvalid = 7030  <br/> |任务挣值方法无效。  <br/> |
|TaskCannotModifyProjectSummary = 7031  <br/> |无法修改项目摘要任务。  <br/> |
|TaskCannotDeleteProjectSummary = 7032  <br/> |无法删除项目摘要任务。  <br/> |
|TaskCannotSetActualCost = 7033  <br/> |无法设置任务的实际成本。  <br/> |
|TaskLevelingDelayInvalid = 7034  <br/> |任务的资源调配延迟无效。  <br/> |
|TaskCannotEditSummary = 7035  <br/> |无法编辑摘要任务。  <br/> |
|TaskCannotCreateSubTasksUnderTasksWithAssignments = 7036  <br/> |无法在具有工作分配的任务下创建子任务。  <br/> |
|TaskCannotDeleteSubProject = 7037  <br/> |无法删除任务的子项目。  <br/> |
|TaskCannotEditExternal = 7038  <br/> |无法编辑外部任务。  <br/> |
|TaskCannotDeleteExternal = 7039  <br/> |无法删除外部任务。  <br/> |
|TaskLinkCannotDeleteExternal = 7040  <br/> |无法删除指向外部任务的链接。  <br/> |
|TaskCannotModifyNullTask = 7041  <br/> |无法修改 Null 任务。  <br/> |
|TaskCannotModifyLeafTaskWithNoAssignment = 7042  <br/> |无法修改没有工作分配的叶任务。  <br/> |
|TaskCannotModifyExternalTask = 7043  <br/> |无法修改外部任务。  <br/> |
|TaskStatusManagerInvalid = 7044  <br/> |任务状态管理器无效。  <br/> |
|TaskLinkCyclicDependency = 7045  <br/> |任务链接具有循环依赖关系。  <br/> |
|TaskCannotCreateOrModifySubTasksUnderTasksWithAssignments = 7046  <br/> |无法在具有工作分配的摘要任务下创建或修改子任务。  <br/> |
|TaskLinkCannotEditExternal = 7047  <br/> |无法编辑外部任务的链接。  <br/> |

<a name="pj15_ErrorCodes_Timesheets"></a>

## <a name="table-28-timesheet"></a>表 28. 时间表 

|时间表错误代码|说明|
|:-----|:-----|
|TimesheetMaxHourPerDayExceeded = 3201  <br/> |超出了时间表每天的最大时数。  <br/> |
|TimesheetHoursPerTSLimitExceeded = 3202  <br/> |超出了时间表的时数限制。  <br/> |
|TimesheetUnverifiedTSLineNotAllowed = 3203  <br/> |此情况下不允许使用未验证的时间表行。  <br/> |
|TimesheetIncorrectMode = 3204  <br/> |时间表模式无效。  <br/> |
|TimesheetInvalidApprover = 3205  <br/> |时间表审批者无效。  <br/> |
|TimesheetFutureReportingNotAllowed = 3206  <br/> |时间表不允许报告未来项。  <br/> |
|TimesheetIncorrectPeriod = 3208  <br/> |时间表时段无效。  <br/> |
|TimesheetPeriodClosed = 3209  <br/> |时间表时段已结束。  <br/> |
|TimesheetPendingLines = 3210  <br/> |时间表行挂起。  <br/> |
|TimesheetInvalidDateRange = 3211  <br/> |时间表日期范围无效。  <br/> |
|TimesheetLineClassDisabled = 3212  <br/> |时间表行类已禁用。  <br/> |
|TimesheetLineHasNonExistentItem = 3213  <br/> |时间表行包含不存在的项。  <br/> |
|TimesheetLineInvalidStatus = 3214  <br/> |时间表行的状态无效。  <br/> |

<a name="pj15_ErrorCodes_UserDelegation"></a>

## <a name="table-29-user-delegation"></a>表 29. 用户委派 

|用户委派错误代码|说明|
|:-----|:-----|
|UserDelegationExpired = 43000  <br/> |用户委派已过期。  <br/> |
|UserDelegationCannotSelfDelegate = 43001  <br/> |用户不能委派给自己。  <br/> |
|UserDelegationInvalidDelegate = 43002  <br/> |用户委派无效。  <br/> |
|UserDelegationInvalidUser = 43003  <br/> |用户对委派无效。  <br/> |
|UserDelegationInvalidDates = 43004  <br/> |用户委派日期无效。  <br/> |
|UserDelegationCannotDoubleDelegate = 43005  <br/> |无法创建两个委派。  <br/> |
|UserDelegationDelegateCannotLogon = 43006  <br/> |用户委派无法登录 Project Server。  <br/> |
|UserDelegationDelegateIsInactive = 43007  <br/> |用户委派处于非活动状态。  <br/> |
|UserDelegationInvalidFilter = 43008  <br/> |用户委派筛选器无效。  <br/> |
|UserDelegationUserCannotLogon = 43010  <br/> |用户无法登录 Project Server。  <br/> |
|UserDelegationUserIsInactive = 43011  <br/> |用户委派处于非活动状态。  <br/> |

<a name="pj15_ErrorCodes_Workflow"></a>

## <a name="table-30-workflow"></a>表 30. 工作流 

|工作流错误代码|说明|
|:-----|:-----|
|WorkflowPhasesCannotCreatePhase = 35000  <br/> |无法创建工作流阶段。  <br/> |
|WorkflowPhasesCannotUpdatePhase = 35001  <br/> |无法更新工作流阶段。  <br/> |
|WorkflowPhasesCannotDeletePhase = 35002  <br/> |无法删除工作流阶段。  <br/> |
|WorkflowPhaseNameIsRequired = 35003  <br/> |工作流 [PHASE_NAME](https://msdn.microsoft.com/library/WebSvcWorkflow.WorkflowDataSet.WorkflowPhaseRow.PHASE_NAME.aspx) 是必需的。  <br/> |
|WorkflowStagesCannotCreateStage = 35004  <br/> |无法创建工作流容器。  <br/> |
|WorkflowStagesCannotUpdateStage = 35005  <br/> |无法更新工作流容器。  <br/> |
|WorkflowStagesCannotDeleteStage = 35006  <br/> |无法删除工作流容器。  <br/> |
|WorkflowStagesProjectsInStage = 35007  <br/> |工作流容器中存在项目。  <br/> |
|WorkflowCannotAccessPDPLibrary = 35008  <br/> |无法访问项目详细信息页库。  <br/> |
|WorkflowInvalidPDPUid = 35009  <br/> |项目详细信息页 GUID 无效。  <br/> |
|WorkflowInvalidCustomFieldUid = 35010  <br/> |自定义域 GUID 无效。  <br/> |
|WorkflowCustomFieldNotWorkflowControlled = 35011  <br/> |自定义域不是工作流控制的。  <br/> |
|WorkflowCustomFieldCannotBeRequiredAndReadOnly = 35012  <br/> |工作流自定义域不能同时为必需和只读。  <br/> |
|WorkflowInvalidWorkflowPhaseUid = 35013  <br/> |工作流 [PHASE_UID](https://msdn.microsoft.com/library/WebSvcWorkflow.WorkflowDataSet.WorkflowPhaseRow.PHASE_UID.aspx) 无效。  <br/> |
|WorkflowInsertWorkflowPhaseNotAllowed = 35014  <br/> |无法插入工作流阶段。  <br/> |
|WorkflowInvalidWorkflowStageUid = 35015  <br/> |工作流 [STAGE_UID](https://msdn.microsoft.com/library/WebSvcWorkflow.WorkflowDataSet.WorkflowStageRow.STAGE_UID.aspx) 无效。  <br/> |
|WorkflowPhaseHasStages = 35016  <br/> |工作流阶段具有容器。  <br/> |
|WorkflowStageNameIsRequired = 35020  <br/> |工作流 [STAGE_NAME](https://msdn.microsoft.com/library/WebSvcWorkflow.WorkflowDataSet.WorkflowStageRow.STAGE_NAME.aspx) 是必需的。  <br/> |
|WorkflowStageAtLeastOnePDPIsRequired = 35021  <br/> |工作流容器至少需要一个项目详细信息页。  <br/> |
|WorkflowCannotStartWorkflow = 35100  <br/> |无法启动工作流。  <br/> |
|WorkflowStatusCannotUpdateStatus = 35101  <br/> |无法更新工作流状态。  <br/> |
|WorkflowOnlyProjectsHaveWorkflow = 35102  <br/> |仅项目可具有工作流。  <br/> |
|WorkflowNoWorkflowsDefined = 35103  <br/> |未定义任何工作流。  <br/> |
|WorkflowInvalidStageForProject = 35104  <br/> |项目的工作流容器无效。  <br/> |
|WorkflowNoWorkflowForProject = 35105  <br/> |项目没有工作流。  <br/> |
|WorkflowCheckinRequiredAndProjectNotCheckedin = 35106  <br/> |必须签入项目才能让工作流工作。  <br/> |
|WorkflowWaitingForRequiredData = 35107  <br/> |工作流正等待所需数据。  <br/> |
|WorkflowFlagCustomFieldsCannotBeRequired = 35108  <br/> |工作流中的标志自定义域不能是必需的。  <br/> |
|WorkflowCannotChangeWorkflow = 35109  <br/> |无法更改工作流。  <br/> |
|WorkflowWorkflowStatusPDPNotAllowed = 35110  <br/> |不允许使用工作流状态的项目详细信息页。  <br/> |
|WorkflowInvalidWorkflowStatusPDPUid = 35111  <br/> |工作流状态项目详细信息页的 GUID 无效。  <br/> |
|WorkflowInvalidStageStatusValue = 35112  <br/> |工作流阶段状态的值无效。 当你在工作流中设置阶段状态时，仅允许使用 [Workflow.StageStatus](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.Workflow.StageStatus.aspx) 中的值 **InProgressRequestSent**、**InProgressRunning** 或 **InProgressWaiting**。  <br/> |
|WorkflowCannotCheckinNotify = 35113  <br/> |无法通知工作流项目已迁入。  <br/> |
|WorkflowCannotCommitNotify = 35114  <br/> |无法通知工作流项目已在计划工具或优化器中提交。  <br/> |
|WorkflowExceptionStartingWorkflow = 35115  <br/> |启动工作流时存在错误。  <br/> |
|WorkflowStatusPDPMustBeSupplied = 35116  <br/> |需要工作流状态的项目详细信息页。  <br/> |
|WorkflowWorkflowProxyAccountNotFound = 35117  <br/> |未找到工作流代理帐户。  <br/> |
|WorkflowInvalidCurrentStage = 35118  <br/> |工作流的当前容器无效。  <br/> |
|WorkflowMultipleStagesInProgress = 35119  <br/> |工作流中有多个容器正在进行。  <br/> |
|WorkflowActivityInvalidArgument = 35120  <br/> |在工作流活动收到无效参数时将会收到的消息。  <br/> |
|WorkflowMTWConfigurationError = 35121  <br/> |Microsoft Azure 工作流配置错误。  <br/> |
|EnterpriseProjectTypeInvalidEnterpriseProjectTypeUid = 35200  <br/> |**ENTERPRISE_PROJECT_TYPE_UID** 无效。  <br/> |
|EnterpriseProjectTypeCannotCreateEnterpriseProjectType = 35201  <br/> |无法创建企业项目类型。  <br/> |
|EnterpriseProjectTypeCannotUpdateEnterpriseProjectType = 35202  <br/> |无法更新企业项目类型。  <br/> |
|EnterpriseProjectTypeCannotDeleteEnterpriseProjectType = 35203  <br/> |无法删除企业项目类型。  <br/> |
|EnterpriseProjectTypeCannotCreateMultipleEnterpriseProjectTypes = 35204  <br/> |无法创建多个企业项目类型。  <br/> |
|EnterpriseProjectTypeCannotUpdateMultipleEnterpriseProjectTypes = 35205  <br/> |无法更新多个企业项目类型。  <br/> |
|EnterpriseProjectTypeInvalidCreatePDPUid = 35206  <br/> |企业项目模板 (EPT) 需要关联的项目详细信息页面 (PDP) 才能使用 EPT 创建项目。 如果 EPT 用于工作流，则当项目详细信息页面 (PDP) 不是*创建*类型时，在 EPT 验证期间会发生此错误。 其他 PDP 类型*正常*用于编辑项目和用于显示工作流相关项目详细信息的*工作流状态*。  <br/> |
|EnterpriseProjectTypeInvalidProjectPlanTemplateUid = 35207  <br/> |[ENTERPRISE_PROJECT_PLAN_TEMPLATE_UID](https://msdn.microsoft.com/library/WebSvcWorkflow.WorkflowDataSet.EnterpriseProjectTypeRow.ENTERPRISE_PROJECT_PLAN_TEMPLATE_UID.aspx) 无效。  <br/> |
|EnterpriseProjectTypeInvalidWorkspaceTemplateName = 35208  <br/> |[ENTERPRISE_PROJECT_WORKSPACE_TEMPLATE_NAME](https://msdn.microsoft.com/library/WebSvcWorkflow.WorkflowDataSet.EnterpriseProjectTypeRow.ENTERPRISE_PROJECT_WORKSPACE_TEMPLATE_NAME.aspx) 无效。  <br/> |
|EnterpriseProjectTypeInvalidWorkflowAssociationUid = 35209  <br/> |[WORKFLOW_ASSOCIATION_UID](https://msdn.microsoft.com/library/WebSvcWorkflow.WorkflowDataSet.EnterpriseProjectTypeRow.WORKFLOW_ASSOCIATION_UID.aspx) 无效。  <br/> |
|EnterpriseProjectTypeCannotReadWssSettings = 35210  <br/> |无法读取 SharePoint 设置。  <br/> |
|EnterpriseProjectTypeCannotReadWssLanguagesAndTemplates = 35211  <br/> |无法读取 SharePoint 语言和网站模板。  <br/> |
|EnterpriseProjectTypeInvalidDepartmentUid = 35212  <br/> |[DEPARTMENT_UID](https://msdn.microsoft.com/library/WebSvcWorkflow.WorkflowDataSet.EnterpriseProjectTypeDepartmentsRow.DEPARTMENT_UID.aspx) 无效。  <br/> |
|EnterpriseProjectTypeInvalidUri = 35213  <br/> |[ENTERPRISE_PROJECT_TYPE_UID](https://msdn.microsoft.com/library/WebSvcWorkflow.WorkflowDataSet.EnterpriseProjectTypeDepartmentsRow.ENTERPRISE_PROJECT_TYPE_UID.aspx) 无效。  <br/> |
|EnterpriseProjectTypeUriRequiresHttp = 35214  <br/> |企业项目类型 URI 需要 HTTP 协议。  <br/> |
|EnterpriseProjectTypeCannotDeleteDefault = 35215  <br/> |无法删除默认的企业项目类型。  <br/> |
|EnterpriseProjectTypeCannotChangeDefault = 35216  <br/> |无法更改默认的企业项目类型。  <br/> |
|EnterpriseProjectTypeHasProjectsCannotDelete = 35217  <br/> |无法删除具有项目的企业项目类型。  <br/> |
|EnterpriseProjectTypeCreatePDPIsRequired = 35218  <br/> |工作流的企业项目模板 (EPT) 需要关联的*创建*类型项目详细信息页面 (PDP) 才能使用 EPT 创建项目。 当 EPT 定义中不包含 PDP 时会出现此错误。 其他 PDP 类型*正常*用于编辑项目和用于显示工作流相关项目详细信息的*工作流状态*。  <br/> |
|EnterpriseProjectTypeOnlyOneCreatePDPAllowed = 35219  <br/> |EPT 定义仅允许使用一个*创建*类型的项目详细信息页。  <br/> |
|EnterpriseProjectTypeHasWorkflowOnlyCreatePDPAllowed = 35220  <br/> |工作流的企业项目模板 (EPT) 需要关联的*创建*类型项目详细信息页面 (PDP) 才能使用 EPT 创建项目。 当工作流 EPT 定义中的 PDP 为另一种类型时出现此错误。 其他 PDP 类型*正常*用于编辑项目和用于显示工作流相关项目详细信息的*工作流状态*。  <br/> |
|EnterpriseProjectTypeInvalidData = 35221  <br/> |企业项目类型的 **WorkflowDataSet** 包含无效数据。  <br/> |
|EnterpriseProjectNoDefaultEnterpriseProjectTypeDefined = 35222  <br/> |未定义默认企业项目类型。  <br/> |
|EnterpriseProjectTypeAtLeastOnePDPIsRequired = 35223  <br/> |企业项目类型至少需要一个项目详细信息页。  <br/> |
|EnterpriseProjectTypeWorkflowStatusPDPNotAllowed = 35224  <br/> |企业项目类型不允许使用工作流状态的项目详细信息页。  <br/> |
|EnterpriseProjectTypeCannotChangeWorkflowAssociation = 35225  <br/> |该项目已有企业项目类型 (EPT)；你无法改变项目的 EPT。  <br/> |

<a name="pj15_ErrorCodes_WSS"></a>

## <a name="table-31-wssinterop-and-objectlinkprovider-sharepoint-integration"></a>表 31. WSSInterop 和 ObjectLinkProvider（SharePoint 集成）

|SharePoint 集成错误代码|说明|
|:-----|:-----|
|WSSCreateSiteFailure = 16400  <br/> |未能为项目工作区创建 SharePoint 网站。  <br/> |
|WSSCannotCreateWebWithBlankName = 16401  <br/> |不能使用空名称创建 SharePoint 网站。  <br/> |
|WSSWebAlreadyExists = 16402  <br/> |SharePoint 网站已存在。  <br/> |
|WSSInvalidProjectUID = 16403  <br/> |项目 GUID 对 SharePoint 项目工作区无效。  <br/> |
|WSSProjectAlreadyHasSpWeb = 16404  <br/> |项目已具有 SharePoint Workspace 网站。  <br/> |
|WSSWebDoesNotExist = 16405  <br/> |SharePoint 网站不存在。  <br/> |
|WSSSpWebAlreadyLinkedToProject = 16406  <br/> |SharePoint 网站已链接到项目。  <br/> |
|WSSWebHierarchyDoesNotExist = 16407  <br/> |SharePoint 网站层次结构不存在。  <br/> |
|WSSSPWebHasChildren = 16408  <br/> |SharePoint 网站具有子网站。  <br/> |
|WSSURIInvalidFormat = 16409  <br/> |SharePoint 网站 URI 的格式无效。  <br/> |
|WSSSyncReportingDataFailed = 16410  <br/> |未能同步 SharePoint 的报告数据。  <br/> |
|WSSWorkspaceUrlPathTooLong = 16411  <br/> |SharePoint 项目工作区 URL 路径太长。  <br/> |
|WSSWorkspaceNameContainsIllegalChars = 16412  <br/> |SharePoint 项目网站名称中的一个或多个字符无效。 项目名称中的下列字符无效：/ " : \< \> | , . ' ? \* #  <br/> |
|WSSInvalidWssServerUid = 16413  <br/> |SharePoint 服务器 GUID 无效。  <br/> |
|WSSSyncUsersFailed = 16414  <br/> |未能将 Project Server 用户与 SharePoint 同步。  <br/> |
|WSSWrongWebTemplateLCID = 16415  <br/> |SharePoint 网站模板区域设置标识符（语言 ID）无效。  <br/> |
|WSSWrongWebTemplate = 16416  <br/> |SharePoint 网站模板无效。  <br/> |
|WSSWebIsNotProjectWorkspace = 16417  <br/> |SharePoint 网站不是项目工作区。  <br/> |
|WSSWebCannotStartOrEndOnPeriod = 16418  <br/> |SharePoint 网站名称不能以句点开头或结尾。  <br/> |
|WSSCannotDeleteSiteCollection = 16419  <br/> |无法删除网站集。  <br/> |
|WSSListUidInvalid = 16420  <br/> |SharePoint 列表 GUID 无效。  <br/> |
|WSSSyncDataSetListUidMismatch = 16421  <br/> |SharePoint 列表 GUID 与同步**数据集**中的列表 GUID 不匹配。  <br/> |
|WSSSyncDataSetMissingProjectSettingsRow = 16422  <br/> |用于与 SharePoint 同步的**数据集**缺少项目设置行。  <br/> |
|WSSSyncDataSetTaskMappingsNotAllowed = 16423  <br/> |**数据集**中不允许将任务映射用于与 SharePoint 同步。  <br/> |
|WSSSyncDataSetWssListUidEmpty = 16424  <br/> |**数据集**中用于与 SharePoint 同步的 SharePoint 列表 GUID 为空。  <br/> |
|WSSSyncDataNotFound = 16425  <br/> |与 SharePoint 的同步中存在数据丢失。  <br/> |
|WSSSyncCriticalDataValidationError = 16426  <br/> |与 SharePoint 的同步中存在严重的数据验证错误。  <br/> |
|WSSSyncSharePointListNotAccessibleError = 16427  <br/> |SharePoint 列表不可访问。  <br/> |
|WSSSyncInvalidEntityUids = 16428  <br/> |实体 GUID 对与 SharePoint 同步无效。  <br/> |
|WSSSyncInvalidSyncData = 16429  <br/> |SharePoint 同步具有无效的数据。  <br/> |
|WSSSyncSPSummaryTaskAssignedToResourceError = 16430  <br/> |SharePoint 同步具有分配给资源的摘要任务。  <br/> |
|WSSSyncInsufficientPermissionsToCreateWinUser = 16431  <br/> |与 SharePoint 同步时，权限不足，无法创建 Windows 用户。  <br/> |
|WSSSyncNoDefaultValueForCustomField = 16432  <br/> |自定义域没有 SharePoint 同步中的默认值。  <br/> |
|WSSOLPCreateLinkFailure = 18000  <br/> |未能为 SharePoint 对象链接提供程序创建链接。  <br/> |
|WSSOLPDeleteWebObjectLinkError = 18001  <br/> |删除 SharePoint 对象链接提供程序中的 Web 对象链接时出错。  <br/> |
|WSSInvalidPermissionsToWssList = 18002  <br/> |权限对 SharePoint 列表无效。  <br/> |
|WSSWebIsNotUnderDefaultCollection = 18003  <br/> |SharePoint 网站不在默认集合中。  <br/> |
|WSSWorkspaceUrlIsNotUnderPrimaryCollection = 18004  <br/> |指定的工作区 url 不在与 Project Server 的示例关联的网站集中。 当前权限模式需要此 URL。  <br/> |
|WSSWorkspacesMustBeRestrictedToDefaultCollection = 18005  <br/> |必须将工作区限制为当前权限模式下的默认网站集。  <br/> |

<a name="pj15_ErrorCodes_ASMXExample"> </a>

## <a name="error-code-example-for-asmx"></a>ASMX 的错误代码示例

要在调用 PSI 方法出现异常时获取错误列表，请将 **SoapException** 对象传递给 [Microsoft.Office.Project.Server.Library.PSClientError](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.PSClientError.aspx) 类构造函数。 然后可以使用 [GetAllErrors](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.PSClientError.GetAllErrors.aspx) 将错误信息存储在 **PSErrorInfo** 数组中并枚举错误，如下例所示。 
  
> [!NOTE]
> **PSErrorInfo** 对象不包括可能需要的全部信息。 例如，如果你使用 **Resource.CheckOutResources**，其中一个资源已经签出，**PSErrorInfo** 将显示每个无法签出的资源失败的原因，但不包括资源名称或 GUID。 有关在基于 ASMX 的应用程序中获取详细信息的方法，请参阅 [CheckOutResources](https://msdn.microsoft.com/library/WebSvcResource.Resource.CheckOutResources.aspx)。 
  
```cs
using System;
using System.Collections.Generic;
using System.Text;
using System.Web.Services.Protocols;
using System.Windows.Forms;
using PSLibrary = Microsoft.Office.Project.Server.Library;
. . .
try
{
    /* Call a PSI method. */
}
catch (SoapException ex)
{
    string errAttributeName;
    string errAttribute;
    string errMess = "".PadRight(30, '=') + "\r\n" + "Error: " + "\r\n";
    PSLibrary.PSClientError error = new PSLibrary.PSClientError(ex);
    PSLibrary.PSErrorInfo[] errors = error.GetAllErrors();
    PSLibrary.PSErrorInfo thisError;
    for (int i = 0; i < errors.Length; i++)
    {
        thisError = errors[i];
        errMess += "\n" + ex.Message.ToString() + "\r\n";
        errMess += "".PadRight(30, '=') + "\r\nPSCLientError Output:\r\n \r\n";
        errMess += thisError.ErrId.ToString() + "\n";
        for (int j = 0; j < thisError.ErrorAttributes.Length; j++)
        {
            errAttributeName = thisError.ErrorAttributeNames()[j];
            errAttribute = thisError.ErrorAttributes[j];
            errMess += "\r\n\t" + errAttributeName +
                       ": " + errAttribute;
        }
        errMess += "\r\n".PadRight(30, '=');
    }
    MessageBox.Show(errMess, "Error", MessageBoxButtons.OK,
        MessageBoxIcon.Error);
}
```

<a name="pj15_ErrorCodes_WCFExample"> </a>

## <a name="error-code-example-for-wcf"></a>WCF 的错误代码示例

要在基于 WCF 的应用程序中调用 PSI 方法获得 **System.ServiceModel.FaultException** 时获取错误列表，可以从 **FaultException** 对象中提取 **PSClientError** 对象。 然后，你可以使用 [GetAllErrors](https://msdn.microsoft.com/library/Microsoft.Office.Project.Server.Library.PSClientError.GetAllErrors.aspx) 将错误信息存储在 **PSErrorInfo** 数组中并枚举错误，如上一个 ASMX 示例中所示。 
  
```cs
using System;
using System.Text;
using System.ServiceModel;
using System.Xml;
using PSLibrary = Microsoft.Office.Project.Server.Library;
. . .
try
{
    /* Call a PSI method. */
}
catch(FaultException fault)
{
    // Use the WCF FaultException, because the ASMX SoapException does not 
    // exist in a WCF-based application.
    WriteFaultOutput(fault);
}
// Get a PSClientError object from the WCF FaultException object, and
// then display the exception details and each error in the PSClientError stack.
private static void WriteFaultOutput(FaultException fault)
{
    string errAttributeName;
    string errAttribute;
    string errOut;
    string errMess = "".PadRight(30, '=') + "\r\n"
        + "Error details: " + "\r\n";
    PSLibrary.PSClientError error = GetPSClientError(fault, out errOut);
    errMess += errOut;
    PSLibrary.PSErrorInfo[] errors = error.GetAllErrors();
    PSLibrary.PSErrorInfo thisError;
    for (int i = 0; i < errors.Length; i++)
    {
        thisError = errors[i];
        errMess += "\r\n".PadRight(30, '=') + "\r\nPSClientError output:\r\n";
        errMess += thisError.ErrId.ToString() + "\n";
        for (int j = 0; j < thisError.ErrorAttributes.Length; j++)
        {
            errAttributeName = thisError.ErrorAttributeNames()[j];
            errAttribute = thisError.ErrorAttributes[j];
            errMess += "\r\n\t" + errAttributeName
                + ": " + errAttribute;
        }
    }
    Console.ForegroundColor = ConsoleColor.Red;
    Console.WriteLine(errMess);
    Console.ResetColor();
}
/// <summary>
/// Extract a PSClientError object from the ServiceModel.FaultException,
/// for use in output of the GetPSClientError stack of errors.
/// </summary>
/// <param name="e"></param>
/// <param name="errOut">Shows that FaultException has more information 
/// about the errors than PSClientError has. FaultException can also contain 
/// other types of errors, such as failure to connect to the server.</param>
/// <returns>PSClientError object, for enumerating errors.</returns>
public static PSLibrary.PSClientError GetPSClientError(FaultException e, 
                                                        out string errOut)
{
    const string PREFIX = "GetPSClientError() returns null: ";
    errOut = string.Empty;
    PSLibrary.PSClientError psClientError = null;
    if (e == null)
    {
        errOut = PREFIX + "Null parameter (FaultException e) passed in.";
        psClientError = null;
    }
    else
    {
        // Get a ServiceModel.MessageFault object.
        var messageFault = e.CreateMessageFault();
        if (messageFault.HasDetail)
        {
            using (var xmlReader = messageFault.GetReaderAtDetailContents())
            {
                var xml = new XmlDocument();
                xml.Load(xmlReader);
                var serverExecutionFault = xml["ServerExecutionFault"];
                if (serverExecutionFault != null)
                {
                    var exceptionDetails = serverExecutionFault["ExceptionDetails"];
                    if (exceptionDetails != null)
                    {
                        try
                        {
                            errOut = exceptionDetails.InnerXml + "\r\n";
                            psClientError = 
                                new PSLibrary.PSClientError(exceptionDetails.InnerXml);
                        }
                        catch (InvalidOperationException ex)
                        {
                            errOut = PREFIX + "Unable to convert fault exception info ";
                            errOut += "a valid Project Server error message. Message: \n\t";
                            errOut += ex.Message;
                            psClientError = null;
                        }
                    }
                    else
                    {
                        errOut = PREFIX + "The FaultException e is a ServerExecutionFault, "
                            + "but does not have ExceptionDetails.";
                    }
                }
                else
                {
                    errOut = PREFIX + "The FaultException e is not a ServerExecutionFault.";
                }
            }
        }
        else // No detail in the MessageFault.
        {
            errOut = PREFIX + "The FaultException e does not have any detail.";
        }
    }
    errOut += "\r\n" + e.ToString() + "\r\n";
    return psClientError;
}

```

<br/>

除了 **PSClientError** 对象中的数据之外，**FaultException** 对象还包含其他类型的错误，例如无法连接到 Project Server。 上一个示例中 **GetPSClientError** 方法的 _errOut_ 参数显示了其他信息。 例如，[QueueCreateProject](https://msdn.microsoft.com/library/WebSvcProject.Project.QueueCreateProject.aspx) 方法中的 **CreateProject4Department ** 代码示例包含显示在 **ProjectCustomFields** 表中设置属性时如何创建错误的注释。 应用程序运行时，_errOut_ 参数包含 **errinfo** 元素和其他数据（在此处从控制台输出格式化）。 
  
```XML
==============================
Error details:
<errinfo xmlns="">
  <dataset name="ProjectDataSet">
    <table name="ProjectCustomFields">
      <row CUSTOM_FIELD_UID="976d3bd9-95ff-40a2-a938-960c410b0341">
        <error id="11704" name="CustomFieldInvalidTypeColumnFilledIn" 
               uid="aa8a2fab-9262-422f-b022-ca1cb12bc75f"></error>
        <error id="11713" name="CustomFieldRequiredValueNotProvided" 
               uid="dc2e2156-86e9-4aac-bede-d07dc44dfedc"></error>
      </row>
    </table>
  </dataset>
</errinfo>
System.ServiceModel.FaultException`1[SvcProject.ServerExecutionFault]: 
ProjectServerError(s) LastError=CustomFieldRequiredValueNotProvided Instructions: 
Pass this into PSClientError constructor to access all error information 
(Fault Detail is equal to SvcProject.ServerExecutionFault).
============================
PSClientError output:
CustomFieldInvalidTypeColumnFilledIn
============================
PSClientError output:
CustomFieldRequiredValueNotProvided
```

<a name="pj15_ErrorCodes_AR"> </a>

## <a name="see-also"></a>另请参阅

- [项目概念性和操作说明文章](project-conceptual-and-how-to-articles.md)
- [SQL Server Profiler](https://msdn.microsoft.com/library/3ad5f33d-559e-41a4-bde6-bb98792f7f1a.aspx)
- [Project Server 2010：出现意外情况时所需的操作](https://blogs.msdn.com/b/brismith/archive/2010/03/24/project-server-2010-what-to-expect-when-you-get-the-unexpected.aspx)
- [ULS Viewer](https://www.codeproject.com/Articles/458052/ULS-Log-Viewer)
    

