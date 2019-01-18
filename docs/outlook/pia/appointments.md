---
title: 约会
TOCTitle: Appointments
ms:assetid: 989a94a8-c1dc-4c5d-ab2b-2cc29a08f8a3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184627(v=office.15)
ms:contentKeyID: 55119805
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 857ece886aab1f572ff24271de92344ba3a0092e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722933"
---
# <a name="appointments"></a>约会

本节提供涉及约会的示例任务。 约会包括活动、会议、定期约会等。 Outlook 使用 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象来表示“日历”文件夹中的约会。

## <a name="in-this-section"></a>本节内容

|主题|说明|
|:----|:----------|
|[创建属于全天事件的约会](how-to-create-an-appointment-that-is-an-all-day-event.md)  |介绍了如何使用 [AllDayEvent](https://msdn.microsoft.com/library/bb610279\(v=office.15\)) 属性来创建属于全天事件的约会。|
|[创建开始时采用太平洋时区且结束时采用东部时区的约会](how-to-create-an-appointment-that-starts-in-the-pacific-time-zone-and-ends-in-the-eastern-time-zone.md)  |介绍了如何创建开始时采用太平洋时区 (UTC-8) 且结束时采用东部时区 (UTC-5) 的约会。|
|[为约会项指定不同的收件人类型](how-to-specify-different-recipient-types-for-an-appointment-item.md)  |介绍了如何使用 [OlMeetingRecipientType](https://msdn.microsoft.com/library/bb623431\(v=office.15\)) 枚举，为约会项指定不同的收件人类型。|
|[使用默认定期模式创建定期约会](how-to-create-a-recurring-appointment-by-using-the-default-recurrence-pattern.md)  |介绍了如何使用默认定期模式创建定期约会。|
|[创建模式为每周一次的定期约会](how-to-create-a-recurring-appointment-that-has-a-weekly-pattern.md)  |介绍了如何创建模式为每周一次的定期约会（例如，约会每个星期一、星期三和星期五发生一次）。|
|[创建使用 YearNth 模式的每年一次定期约会](how-to-create-an-annual-recurring-appointment-that-uses-a-yearnth-pattern.md)  |介绍了如何创建定期模式为每年一次的约会（如在 6 月的第一个星期一等特定日期发生）。|
|[在定期约会系列中查找特定约会](how-to-find-a-specific-appointment-in-a-recurring-appointment-series.md)  |介绍了如何返回表示定期约会系列中特定约会的 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象。|
|[在定期约会系列中创建例外约会](how-to-create-an-exception-appointment-in-a-recurring-appointment-series.md)  |介绍了如何使用 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 对象创建约会标准定期模式的例外。|
|[创建约会项提醒](how-to-create-a-reminder-for-an-appointment-item.md)  |介绍了如何使用 [ReminderSet](https://msdn.microsoft.com/library/bb624262\(v=office.15\)) 属性创建约会项提醒。|
|[将约会 XML 数据导入 Outlook 约会对象](how-to-import-appointment-xml-data-into-outlook-appointment-objects.md)  |读取 XML 格式的约会数据，将此类数据保存到默认日历的 Outlook AppointmentItem 对象中，然后以数组的形式返回这些约会对象。|

## <a name="see-also"></a>另请参阅

- [日历](calendar.md)
- [会议请求](meeting-requests.md)
- [我如何...（Outlook 2013 PIA 参考）](how-do-i-outlook-2013-pia-reference.md)

