---
title: Office 中的兼容性问题
manager: scotv
ms.date: 04/12/2016
ms.audience: Developer
ms.assetid: dd279238-ae75-4ad9-b9e5-364924090485
description: 获取有关遥测日志中显示的关于 Office 产品中可能存在的兼容性问题的详细信息。
localization_priority: Priority
ms.openlocfilehash: f0c2462662121ee6ec7944dde5a01e2964fc28cf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357503"
---
# <a name="compatibility-issues-in-office"></a>Office 中的兼容性问题

获取有关遥测日志中显示的关于 Office 产品中可能存在的兼容性问题的详细信息。
  
下表列出了有关遥测日志中出现的问题的信息。有关遥测日志的详细信息，请参阅[疑难解答遥测日志的 Office 文件和自定义解决方案](troubleshooting-office-files-and-custom-solutions-with-the-telemetry-log.md)。
  
有关 Office 2013 以来已更改或删除的功能的信息，请参阅 [Office 2016 for Windows 中的更改](https://technet.microsoft.com/library/mt715497%28v=office.16%29.aspx)。
  
## <a name="controls"></a>控件
<a name="OEV_CompatIssues_Controls"> </a>

如果文件包含在 Office 中或计算机操作系统上不受支持的控件，则会出现这些消息。
  
**表 1.遥测日志中显示的有关控件的问题**

|**事件 ID**|**引入版本**|**受影响的应用程序**|**其他信息**|**标题**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|10000  <br/> |Office 2013  <br/> |所有 Office 2013  <br/> ||警告：Visual Basic 6.0 控件  <br/> |文件使用不适用于 64 位版本的 Office 或 32 位版本的 Office（它们在使用 ARM 处理器的设备上运行）的 Visual Basic 6.0 控件。如果您希望控件在这些环境中对 Office 应用程序可用，请将控件替换为受支持的控件。  <br/> |
|10001  <br/> |Office 2013  <br/> |所有 Office 2013  <br/> |[链接](https://msdn.microsoft.com/vbasic/ms788708.aspx) <br/> |控件：64 位操作系统上的 Visual Basic 6.0 控件  <br/> |文件使用不适用于 64 位版本的 Office 的 Visual Basic 6.0 控件。Visual Basic 6.0 运行时文件是 32 位的且仅在 32 位操作系统或 WOW 模拟环境中受支持。  <br/> |
|10002  <br/> |Office 2013  <br/> |所有 Office 2013  <br/> |[链接](https://msdn.microsoft.com/vbasic/ms788708.aspx) <br/> |控件：带 ARM 处理器的设备上的 Visual Basic 6.0 控件  <br/> |文件使用不适用于带 ARM 处理器的设备的 Visual Basic 6.0 控件。  <br/> |
|10003  <br/> |Office 2013  <br/> |所有 Office 2013  <br/> |[链接](https://technet.microsoft.com/zh-CN/library/cc179181.aspx) <br/> |控件：Microsoft 日历控件  <br/> |文件使用 Microsoft 日历控件 (Mscal.ocx)，它是早期版本的 Access 的一项功能，此功能在 Office 2013 中不可用。此控件将无法运行，因为它未安装到主机上。将其他日期选取器控件用作备选项，如 **Date Picker Content Control**（在 Word 2013 中）或 Windows **DatePicker** 控件（在 Windows 公共控件中）。  <br/> 有关详细信息，请参阅[替换 Access 2010 应用程序中的日历控件](https://msdn.microsoft.com/library/dc6ba80d-b1fa-4596-b484-5e729cae4d70)。  <br/> |
|10004  <br/> |Office 2013  <br/> |所有 Office 2013  <br/> |[链接](https://support.microsoft.com/kb/972129) <br/> |Office Web 组件  <br/> |文件使用 Office Web 组件 (MSOWC.dll) 控件。此控件将无法运行，因为 Office Web 组件未安装到此计算机上且未随 Office 2013 附带。若要使用此控件，请单独安装 Office Web 组件。  <br/> 有关详细信息，请参阅[查找 Office Web 组件编程文档和示例](https://support.microsoft.com/kb/319793) <br/> |
|10005  <br/> |Office 2013  <br/> |所有 Office 2013  <br/> |[链接](https://office.microsoft.com/en-us/access-help/embedded-object-and-activex-control-policy-settings-error-HA101825674.aspx?CTT=1) <br/> |控件：已注销 ActiveX 控件  <br/> |文件使用未在主机上注册的 ActiveX 控件。若要使用此控件，请在主机上注册它。  <br/> |
   
## <a name="removed-and-deprecated-members-in-the-object-model"></a>对象模型中的已删除和已弃用成员
<a name="OEV_CompatIssues_Removed"> </a>

如果加载项或已启用宏的文档代码使用已从应用程序的对象模型中删除的对象、成员、集合、枚举或常量，则会显示这些消息。 
  
**表 2.遥测日志中显示的有关已删除和已弃用成员的问题**

|**事件 ID**|**引入版本**|**受影响的应用程序**|**其他信息**|**标题**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|10103  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> |[链接](https://support.microsoft.com/kb/2445062) <br/> |OM 已移除: 自定义 XML 功能  <br/> | 自定义 XML 功能已从 Word 中移除。 以下方法和属性已被隐藏，如果访问它们，则将返回运行时错误：<br/><br/>- **XMLNodes.Add** 方法  <br/>- **Document.XMLHideNamespaces** 属性  <br/>- **Document.XMLSaveDataOnly** 属性  <br/>- **Document.XMLSchemaViolations** 属性  <br/>- **XMLSchemaViolations** 对象及其所有成员  <br/>- **XMLSchemaViolation** 对象及其所有成员  <br/>如果指定 **WdTaskPanes** 枚举的 **wdTaskPaneXMLStructure** 常量 (5)，则为 - **Application.TaskPanes**  <br/>- **Options.PrintXMLTag** 属性  <br/>- **View.ShowXMLMarkup** 属性  <br/>- **XMLChildNodeSuggestions** 集合及其所有成员  <br/>- **XMLChildNodeSuggestion** 对象及其所有成员  <br/>- **Selection.XMLParentNode** 属性  <br/>- **Range.XMLParentNode** 属性  <br/> |
|10113  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已移除: 智能标记功能  <br/> | 从 Word 中删除 SmartTags 功能。以下方法和属性已被隐藏，如果访问它们，则将返回运行时错误：<br/>- **SmartTag** 对象和成员  <br/>- **SmartTags** 集合和成员  <br/>- **SmartTagAction** 对象和成员  <br/>- **SmartTagActions** 集合和成员  <br/>- **SmartTagType** 对象和成员  <br/>- **SmartTagTypes** 集合和成员  <br/>- **XMLNode.SmartTag** 属性  <br/><br/>  以下方法已被隐藏，如果访问它们，则将自行失败：  <br/>- **Document.CheckNewSmartTags** 方法  <br/>- **Document.RecheckSmartTags** 方法  <br/>- **Document.RemoveSmartTags** 方法  <br/><br/>以下属性已被隐藏，如果访问它们，则将始终返回 False：  <br/>- **Document.EmbedSmartTags** 属性  <br/>- **Document.SmartTagsAsXMLProps** 属性  <br/>- **Options.LabelSmartTags** 属性  <br/>- **Options.DisplaySmartTagButtons** 属性  <br/>- **EmailOptions.EmbedSmartTag** 属性  <br/><br/>以下属性已被隐藏，如果访问它们，则将始终返回 True：  <br/>- **View.DisplaySmartTags** 属性<br/><br/>  以下属性已被隐藏，如果访问它们，则将始终返回一个空集合：  <br/>- **Application.SmartTagTypes** 属性  <br/>- **Document.SmartTags** 属性  <br/>- **Range.SmartTags** 属性  <br/>- **Selection.SmartTags** 属性  <br/> |
|10115  <br/> |Office 2013  <br/> |Word 2013、Outlook 2013  <br/> ||OM 已移除: AutoSummary 功能  <br/> | 已从 Word 中删除 AutoSummary 功能。以下方法和属性已被隐藏，如果访问它们，则将返回运行时错误：<br/>- **Document.AutoSummarize** 方法  <br/>- **Document.ShowSummary** 属性  <br/>- **Document.SummaryViewMode** 属性  <br/>- **Document.SummaryLength** 属性  <br/> |
|10116  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已移除: 条码功能  <br/> | 从 Word 中删除信封的 Barcode 功能。以下属性已被隐藏，如果访问它们，则将始终返回 FALSE：<br/>- **Envelope.DefaultPrintBarCode** 属性  <br/>- **MailingLabel.DefaultPrintBarCode** 属性  <br/> |
|10117  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已移除: Window.DocumentMapPercentWidth 属性  <br/> |**Window.DocumentMapPercentWidth** 属性已在 Word 中隐藏。 如果访问此属性，则将引发运行时错误。  <br/> |
|10122  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已移除: Application.FileSearch  <br/> |已从 Office 2007 中删除 **Application.FileSearch**。如果访问此属性，则将返回错误。若要解决此问题，请使用 [FileSystemObject](https://msdn.microsoft.com/library/7ad2dad3-c6d8-90a6-77a5-c712da8316f3%28Office.15%29.aspx) 以递归方式搜索目录来查找特定文件。  <br/> |
|10145  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 已移除: Application.FileSearch  <br/> |在 Office 2007 中删除 **Application.FileSearch** 属性。如果访问此属性，则将返回错误。若要解决此问题，请使用 [FileSystemObject](https://msdn.microsoft.com/library/7ad2dad3-c6d8-90a6-77a5-c712da8316f3%28Office.15%29.aspx) 以递归方式搜索目录来查找特定文件。  <br/> |
|10154  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 已移除: 智能标记功能  <br/> | 从 Excel 中删除 SmartTags 功能。以下属性已被隐藏，如果访问它们，则将始终返回 FALSE：  <br/>- **Application.SmartTagRecognizers** 属性  <br/><br/>以下方法和属性已被隐藏，如果访问它们，则将返回运行时错误：  <br/>- **SmartTag** 对象和成员  <br/>- **SmartTags** 集合和成员  <br/>- **SmartTagAction** 对象和成员  <br/>- **SmartTagActions** 集合和成员  <br/>- **SmartTagOptions** 集合和成员  <br/>- **SmartTagRecognizer** 对象和成员  <br/>- **SmartTagRecognizers** 集合和成员  <br/><br/>  以下方法已被隐藏，如果访问它们，则将自行失败：  <br/>- **Workbook.RecheckSmartTags** 方法  <br/><br/>以下属性已被隐藏，如果访问它们，则将始终返回一个空集合：  <br/>- **Workbook.SmartTagOptions** 属性  <br/>- **Worksheet.SmartTags** 属性  <br/>- **Range.SmartTags** 属性  <br/>- **IRange.SmartTags** 属性  <br/>- **DialogSheet.SmartTags** 属性  <br/>- **IDialogSheet.SmartTags** 属性  <br/> |
|10155  <br/> |Office 2013  <br/> |所有 Office 2013  <br/> ||OM 已移除: ToolbarButton.Edit 方法  <br/> |已删除 CommandBar 按钮编辑器。如果调用它，则此方法自行失败。可使用 [CommandBarButton.PasteFace](https://msdn.microsoft.com/library/1c4179c4-b6b5-527f-5027-25ced8ee907d%28Office.15%29.aspx) 方法或使用 [CommandBarButton.Picture](https://msdn.microsoft.com/library/b9a2d133-23a8-ac09-8b8b-08eda1210717%28Office.15%29.aspx) 和 [CommandBarButton.Mask](https://msdn.microsoft.com/library/de7179ac-6b39-2323-d84a-23abe3ed3167%28Office.15%29.aspx) 属性将自定义图像应用于旧的 CommandBar 按钮。  <br/> |
|10159  <br/> |Office 2016  <br/> |Word  <br/> ||OM 已禁用：SkyDriveSignInOption  <br/> |SkyDriveSignInOption 已禁用。改为使用 CloudSignInOption。  <br/> |
   
## <a name="behavior-changes-in-the-object-model"></a>对象模型中的行为更改
<a name="OEV_CompatIssues_Changed"> </a>

如果外接程序或已启用宏的文档代码使用其行为与早期版本的 Office 中的行为不同的对象、成员、集合、枚举或常量，则会显示这些消息。
  
**表 3. 遥测日志中显示的有关行为更改的问题**

|**事件 ID**|**引入版本**|**受影响的应用程序**|**其他信息**|**标题**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|10156  <br/> |Office 2016  <br/> |Word  <br/> ||OM 行为更改：检测到使用保存事件  <br/> |兼容性检查器检测到使用保存事件，这可能会在实时共同创作中导致不需要的体验。由于这些应用场景中的保存频率更高，您的解决方案在实时共同创作中可能无法按预期工作。我们建议在频繁保存期间调整限制的解决方案。或者，使用组策略禁用实时共同创作。  <br/> |
|10160  <br/> |Office 2016  <br/> |Word、Excel、PowerPoint  <br/> ||OM 行为更改：Application.DisplayDocumentInformationPanel  <br/> |作为 InfoPath 产品弃用的一部分，文档信息面板已被弃用。查询此属性将始终返回 false。对此属性的设置因应用程序而异。将其设置为 true 将显示 Word 和 PowerPoint 的属性面板，但对 Excel 不执行任何操作。将其设置为 false 不对所有应用执行任何操作。  <br/> |
|10161  <br/> |Office 2016  <br/> |Word  <br/> ||OM 行为更改：ContentControl.DropdownListEntries  <br/> |作为 InfoPath 产品弃用的一部分，文档信息面板已被弃用。针对 SharePoint 查阅属性时，不再支持此 API 的行为。它按预期与其他类型的列表条目合作。  <br/> |
|10157  <br/> |Office 2016  <br/> |PowerPoint  <br/> ||OM 行为更改：Presentation.InMergeMode 属性  <br/> |将共同创作替换为新冲突解决方案窗口时，在文档窗口中显示旧合并模式。如果在这种情况下访问，则 Presentation.InMergeMode 属性将返回 False。  <br/> |
|10106  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 行为更改: Application.FormulaBarHeight 属性  <br/> |[Application.FormulaBarHeight 属性 (Excel)](https://msdn.microsoft.com/library/ff377046-06cb-9cf7-32f5-773da447c184%28Office.15%29.aspx) 属性已被更改。如果访问此属性，则将读取和编写与 Excel 中的活动窗口关联的编辑栏的高度。若要在 Excel 中更改另一个窗口的编辑栏高度，请在激活此窗口后设置 **Application.FormulaBarHeight** 属性。  <br/> |
|10107  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 行为更改: Workbook.Protect 方法  <br/> |无法在 Excel 中保护窗口结构（高度、宽度、最小化状态或最大化状态）。如果调用，则 [Workbook.Protect 方法 (Excel)](https://msdn.microsoft.com/library/0e270b93-7b0b-cc68-c7c0-4002024f4292%28Office.15%29.aspx) 方法不会保护工作簿窗口结构，不管 Windows 参数的值如何。  <br/> |
|10140  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 行为更改: Table.AllowPageBreaks  <br/> |**Table.AllowPageBreaks** 属性已被隐藏且始终返回 True。若要实现相同的行为，请使用 [ParagraphFormat.KeepTogether 属性 (Word)](https://msdn.microsoft.com/library/7cc4cade-f986-8dad-a1b3-e1fade4c6825%28Office.15%29.aspx) 和 [ParagraphFormat.KeepWithNext 属性 (Word)](https://msdn.microsoft.com/library/5fc8ad97-d839-7837-04c7-dac2efe1d1c2%28Office.15%29.aspx) 属性。  <br/> |
   
## <a name="hidden-members-in-the-object-model"></a>对象模型中的已隐藏成员
<a name="OEV_CompatIssues_Hidden"> </a>

如果加载项或已启用宏的文档代码使用已在应用程序的对象模型中隐藏的对象、成员、集合、枚举或常量，则会显示这些消息。
  
**表 4. 遥测日志中显示的有关隐藏成员的问题**

|**事件 ID**|**引入版本**|**受影响的应用程序**|**其他信息**|**标题**|**说明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|10158  <br/> |Office 2016  <br/> |Excel  <br/> ||OM 已隐藏：Presentation.WorksheetFunction.Forecast（所有）方法  <br/> |WorksheetFunction.Forecast 方法已隐藏。如果调用，则该方法的行为类似于在 Excel 2013 中的行为。它保留部分对象模型以实现向后兼容，但您应该在新的应用程序中使用 WorksheetFunction.Forecast_Linear。  <br/> |
|10109  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Document.UpdateSummaryProperties 方法  <br/> |AutoSummary 功能已从 Word 中移除。 如果调用 **Document.UpdateSummaryProperties** 方法，则将引发运行时错误。  <br/> |
|10110  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Comment.Delete 方法  <br/> |注释器可以直接答复 Word 中的其他注释。如果调用 **Comment.Delete** 方法，则此方法会删除单个注释并在文档中保留所有答复，这与早期版本的 Office 的功能类似。若要删除注释的整个线程，请使用 **Comment.DeleteRecursively** 方法。若要答复注释，请使用 **Comment.Replies.Add** 方法。  <br/> |
|10111  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Comment.Author 属性  <br/> |Word 中的注释现已与联系人关联。如果访问 **Comment.Author** 属性，则其行为将类似于早期版本的 Office 的行为。若要访问注释器的名称，请使用与注释关联的 **Contact** 对象的 Name 属性。  <br/> |
|10112  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Comment.Initial 属性  <br/> |默认情况下，注释器的缩写不会与 Word 中的注释一起显示。如果访问 **Comment.Initial** 属性，则其行为将类似于早期版本的 Office 的行为。但是，打印的文档仍显示注释的缩写。  <br/> |
|10114  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Comment.ShowTip 属性  <br/> |默认情况下，显示与 Word 中的注释关联的屏幕提示。如果访问 **Comment.ShowTip** 属性，则始终返回 FALSE。  <br/> |
|10118  <br/> |Office 2013  <br/> |Word 2013、Outlook 2013  <br/> ||OM 已隐藏: Options.BackgroundOpen 属性  <br/> |无法在 Word 中的后台打开大型 Web 文档。如果访问 [Options.BackgroundOpen Property (Word)](https://msdn.microsoft.com/library/eff86857-9b2b-2e38-17cc-17c0f6f06c06%28Office.15%29.aspx) 属性，则始终返回 FALSE 且不能将其设置为任何其他值。  <br/> |
|10119  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Document.ApplyQuickStyleSet 方法  <br/> |已在 Word 中隐藏 **Document.ApplyQuickStyleSet** 方法。如果调用此方法，则它将通过更改文档的样式集来继续起到在 Office 2007 中一样的作用。若要使用 Office 2010 以及更高版本的新功能，请替换为 [Document.ApplyQuickStyleSet2 方法 （Word）](https://msdn.microsoft.com/library/7ed6e6ac-fe0f-388e-65fa-edd711d30926%28Office.15%29.aspx) 方法。  <br/> |
|10120  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Document.SaveAs 方法  <br/> |"另存为"功能的行为类似于早期版本的 Word 的行为。 如果调用，则 **Document.SaveAs** 方法的行为类似于在 Office 2007 中的行为。 此外，将 **SaveAs2** 方法添加到包含 Office 2010 中引入的属性的 Document 对象。 若要使用 Office 2010 以及更高版本的新功能，请将 **Document.SaveAs** 方法替换为 [Document.SaveAs2 方法 (Word)](https://msdn.microsoft.com/library/aa491007-0e31-26f5-3a5e-477381529b6e%28Office.15%29.aspx)。  <br/> |
|10121  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Assistant 和 AnswerWizard 功能  <br/> | 已在 Word 中隐藏 Assistant 和 AnswerWizard 功能。  <br/><br/>以下属性已被隐藏但保留部分对象模型以实现向后兼容。建议不要在新的 Office 解决方案中使用它们：  <br/>- **Application.Assistant** 属性  <br/>- **Application.AnswerWizard** 属性  <br/><br/>将隐藏下列属性。 如果访问它们，则将返回运行时错误：  <br/>- **Global.Assistant** 属性  <br/>- **Global.AnswerWizard** 属性  <br/> |
|10123  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Options.WPHelp  <br/> |**Options.WPHelp** 属性已被隐藏。  <br/> |
|10124  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Options.SetWPHelpOptions  <br/> |**Options.SetWPHelpOptions** 属性已被隐藏。如果访问此属性，则将返回错误。  <br/> |
|10125  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Options.WPDocNavKeys  <br/> |**Options.WPDocNavKeys** 属性已被隐藏。如果访问此属性，则将始终返回 False。  <br/> |
|10126  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Options.BlueScreen  <br/> |**Options.BlueScreen** 属性已被隐藏。如果访问此属性，则将始终返回 False。  <br/> |
|10127  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Options.AllowFastSave  <br/> |**Options.AllowFastSave** 已被隐藏。<br/> |
|10128  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Application.DisplayStatusBar  <br/> |**Application.DisplayStatusBar** 属性已被隐藏。改用 **Application.CommandBars("Status Bar")** Visible。  <br/> |
|10129  <br/> |Office 2013  <br/> |Word 2013Outlook 2013  <br/> ||OM 已隐藏: Document.HTMLProject  <br/> |**Document.HTMLProject** 已被隐藏。如果访问此属性，则将返回错误。  <br/> |
|10130  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Document.Versions  <br/> |删除版本功能，因此将隐藏 **Document.Versions** 属性。如果访问此属性，则将返回错误。  <br/> |
|10131  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Document.Route  <br/> |删除传送名单功能，因此将隐藏 **Document.Route** 方法。如果访问方法，则将返回错误。  <br/> |
|10132  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Document.HasRoutingSlip  <br/> |删除传送名单功能，因此将隐藏 **Document.HasRoutingSlip** 属性。如果访问此属性，则将返回错误。  <br/> |
|10133  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Document.Routed  <br/> |删除传送名单功能，因此将隐藏 **Document.Routed** 属性。如果访问此属性，则将返回错误。  <br/> |
|10134  <br/> |Office 2013  <br/> |Word 2013、Outlook 2013  <br/> ||OM 已隐藏: Document.RoutingSlip  <br/> |删除传送名单功能，因此将隐藏 **Document.RoutingSlip** 属性。如果访问此属性，则将返回错误。  <br/> |
|10135  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: 图表 OM  <br/> | **Diagram** 对象以及与 **Diagram** 对象关联的属性和方法已被隐藏。如果访问它们，则以下成员会生成错误：<br/>- **Shapes.AddDiagram** <br/>- **Shape.Diagram** <br/>- **Shape.DiagramNode** <br/>- **Shape.HasDiagram** <br/>- **ShapeHasDiagramNode** <br/>- **ShapeRange.DiagramNode** <br/>- **ShapeRange.HasDiagram** <br/>- **ShapeRange.HasDiagramNode** <br/> |
|10136  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: ShapeRange.Activate  <br/> | 隐藏 Word 图片对象，因此还将隐藏用于将图片转换为 Word 图片对象的方法。这些方法包括：  <br/>- **InlineShape.Activate** <br/>- **Shape.Activate** <br/>- **ShapeRange.Activate** <br/><br/>  如果使用这些方法，则将生成错误。  <br/> |
|10137  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Shape.Activate  <br/> | 隐藏 Word 图片对象，因此还将隐藏用于将图片转换为 Word 图片对象的方法。这些方法包括：  <br/>- **InlineShape.Activate** <br/>- **Shape.Activate** <br/>- **ShapeRange.Activate** <br/><br/>如果使用这些方法，则将生成错误。  <br/> |
|10138  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: InlineShape.Activate  <br/> | 隐藏 Word 图片对象，因此还将隐藏用于将图片转换为 Word 图片对象的方法。这些方法包括：  <br/>- **InlineShape.Activate** <br/>- **Shape.Activate** <br/>- **ShapeRange.Activate** <br/><br/>如果使用这些方法，则将生成错误。  <br/> |
|10139  <br/> |Office 2013  <br/> |Word 2013  <br/> ||OM 已隐藏: Shapes.AddChart  <br/> |**Shapes.AddChart** 方法已被因此。它保留部分对象模型以实现向后兼容，但不应在新的应用程序中使用它。改用 **Shapes.AddChart2** 方法。  <br/> <br/>**注意**：**Shapes.AddChart2** 方法将默认标题应用于新图表。 如果需要在将图表添加到文件后更改图表的标题，请使用 **Chart.ChartTitle** 属性或手动编辑标题。           |
|10141  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Application.ShowWindowsInTaskbar  <br/> |**Application.ShowWindowinTaskbar** 属性已被隐藏。如果访问此属性，则将始终返回 True。  <br/> |
|10142  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: HangulHanjaConversionDictionaries.BuiltinDictionary  <br/> |**HangulHanjaConversionDictionaries.BuiltinDictionary** 属性已被隐藏。如果访问此属性，则将返回 Null。  <br/> |
|10143  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: Template.AutoTextEntries  <br/> |自动图文集现在是一类构建基块。您可以使用 [Template.BuildingBlockEntries 属性 (Word)](https://msdn.microsoft.com/library/498280ab-a174-7b11-92af-afec477c44be%28Office.15%29.aspx) 或 [Template.BuildingBlockTypes 属性 (Word)](https://msdn.microsoft.com/library/9250d107-4943-c0bf-b11d-08aded886ef2%28Office.15%29.aspx) 属性访问构建基块。  <br/> 默认情况下，自动图文集将保存在 normal.dotm 中  <br/> |
|10144  <br/> |Office 2013  <br/> |Word 2013, Outlook 2013  <br/> ||OM 已隐藏: View.RevisionsMode  <br/> |**View.RevisionsMode** 属性已被隐藏。请改用 [View.MarkupMode 属性 (Word)](https://msdn.microsoft.com/library/2db71940-c39d-b8ec-2732-f3f406af3b7d%28Office.15%29.aspx) 属性。  <br/> |
|10146  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 已隐藏: ISlicerCache.ClearManualFilter  <br/> |已将 ISlicerCache 对象的方法 **ClearManualFilter** 标记为隐藏。它保留部分对象模型以实现向后兼容，但不应在新的应用程序中使用它。  <br/> |
|10147  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 已隐藏: _Application.ShowWindowsInTaskbar  <br/> |属性 **\_Application.ShowWindowsInTaskbar** 已被隐藏。 它保留部分对象模型以实现向后兼容，但不应在新的应用程序中使用它。  <br/> |
|10148  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 已隐藏: _Application.SaveISO8601Dates  <br/> |属性 **\_Application.SaveISO8601Dates** 已被隐藏。 它保留部分对象模型以实现向后兼容，但不应在新的应用程序中使用它。  <br/> |
|10149  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 已隐藏: SlicerCache.ClearManualFilter  <br/> |已将 SlicerCache 对象的方法 **ClearManualFilter** 标记为隐藏。它保留部分对象模型以实现向后兼容，但不应在新的应用程序中使用它。  <br/> |
|10150  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 已隐藏: _Application.Assistant  <br/> |属性 **\_Application.Assistant** 已被隐藏。 它保留部分对象模型以实现向后兼容，但不应在新的应用程序中使用它。  <br/> |
|10151  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 已隐藏: _Application.AnswerWizard  <br/> |属性 **\_Application.Assistant** 已被隐藏。 如果访问此属性，则将返回运行时错误。  <br/> |
|10152  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 已隐藏: _Global.Assistant  <br/> |属性 **\_Global.Assistant** 已被隐藏。 它保留部分对象模型以实现向后兼容，但不应在新的应用程序中使用它。  <br/> |
|10153  <br/> |Office 2013  <br/> |Excel 2013  <br/> ||OM 已隐藏: Shapes.AddChart  <br/> |**Shapes.AddChart** 方法已被因此。它保留部分对象模型以实现向后兼容，但不应在新的应用程序中使用它。改用 **Shapes.AddChart2** 方法。  <br/> <br/>**注意**：**Shapes.AddChart2** 方法将默认标题应用于新图表。 如果需要在将图表添加到文件后更改图表的标题，请使用 **Chart.ChartTitle** 属性或手动编辑标题。           |
   
## <a name="see-also"></a>另请参阅

- [Office 中的兼容性和遥测](https://technet.microsoft.com/library/f1a9a3c6-a3d3-44c6-aec8-14cd834ebaeb) 
- [Office 开发人员中心](https://msdn.microsoft.com/office/aa905340.aspx)
- [疑难解答遥测日志的 Office 文件和自定义解决方案](troubleshooting-office-files-and-custom-solutions-with-the-telemetry-log.md)
- [Office 应用程序兼容性论坛](https://social.technet.microsoft.com/Forums/officesetupdeploy/threads)
    

