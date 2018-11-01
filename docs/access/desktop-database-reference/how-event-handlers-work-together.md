---
title: 事件处理程序如何协同工作
TOCTitle: How Event Handlers Work Together
ms:assetid: 02122824-881e-0bb8-cba1-c963024790ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248788(v=office.15)
ms:contentKeyID: 48542951
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 19f60c196c110787eb7baf57646a9d5d4996fdf0
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877826"
---
# <a name="how-event-handlers-work-together"></a>事件处理程序如何协同工作


**适用于**： Access 2013、 Office 2013



除非您正在用 Visual Basic 编程，否则不管实际上您是否处理所有事件，都必须实现 **Connection** 和 **Recordset** 事件的所有事件处理程序。必须完成的实现工作量取决于编程语言。有关详细信息，请参阅 [ADO 事件实例化（按语言）](https://msdn.microsoft.com/library/jj250244\(v=office.15\))。

## <a name="paired-event-handlers"></a>成对的事件处理程序

每个 Will 事件处理程序都有关联的 Complete 事件处理程序。例如，应用程序更改字段值时，将调用 **WillChangeField** 事件处理程序。如果更改是可接受的，则应用程序将保持 **adStatus** 参数不变，并执行操作。操作完成后， **FieldChangeComplete** 事件将通知应用程序操作已完成。如果操作成功完成， **adStatus** 将包含 **adStatusOK** ；否则， **adStatus** 将包含 **adStatusErrorsOccurred** ，并且您必须检查 **Error** 对象，以确定产生错误的原因。

调用 **WillChangeField** 时，您可能决定不进行更改。在此情况下，请将 **adStatus** 设置为 **adStatusCancel** 。这样，操作将取消，并且 **FieldChangeComplete** 事件将收到一个 **adStatus** 值： **adStatusErrorsOccurred** 。 **Error** 对象将包含 **adErrOperationCancelled** ，以便 **FieldChangeComplete** 处理程序知道操作已取消。但是，在更改 **adStatus** 参数的值之前，您需要对它进行检查，因为，如果在进入过程时将该参数设置为 **adStatusCantDeny** ，那么将 **adStatus** 设置为 **adStatusCancel** 是无效的。

有时，操作可以引发多个事件。例如，对于 **Field** 更改和 **Record** 更改， **Recordset** 对象会提供有成对的事件。应用程序更改 **Field** 的值时，将调用 **WillChangeField** 事件处理程序。如果它确定操作可以继续，还会引发 **WillChangeRecord** 事件处理程序。如果此处理程序也允许事件继续，将执行更改，并调用 **FieldChangeComplete** 和 **RecordChangeComplete** 事件处理程序。调用特定操作的 Will 事件处理程序的顺序是未定义的，所以编写的代码应当避免依赖于按特定序列调用处理程序。

在实例中，当引发多个 Will 事件时，其中的一个事件可能会取消挂起的操作。例如，如果应用程序更改了 **Field** 的值，通常会调用 **WillChangeField** 和 **WillChangeRecord** 事件处理程序。但是，如果在第一个事件处理程序中取消了操作，则会通过 **adStatusOperationCancelled** 立即调用该处理程序关联的 Complete 处理程序。这样，永远不会调用第二个处理程序。但是，如果第一个事件处理程序允许事件继续，则会调用其他事件处理程序。如果这时它取消了操作，则两个 Complete 事件都会像在前面的示例中一样被调用。

## <a name="unpaired-event-handlers"></a>不成对的事件处理程序

只要传递给事件的状态不是**adStatusCantDeny**，可以通过在*Status*参数返回**adStatusUnwantedEvent**将关闭的任何事件的事件通知。 例如，第一次调用 Complete 事件处理程序时，可以返回 **adStatusUnwantedEvent** 。 随后只会收到 Will 事件。 但是，一些事件可以由于多个原因而触发。 在这种情况下，事件将没有*Reason*参数。 返回 **adStatusUnwantedEvent** 时，只有当事件由于特定原因而发生时，您才会停止收到该事件的通知。 换句话说，对于每个可能触发事件的原因，您都有可能收到通知。

如果需要检查将在操作中使用的参数，则可以使用单个 Will 事件处理程序。可以修改这些操作参数或取消操作。

或者，保持 Complete 事件通知处于启用状态。第一次调用 Will 事件处理程序时，返回 **adStatusUnwantedEvent** 。随后，您只会收到 Complete 事件。

单个 Complete 事件处理程序可以用于管理异步操作。每个异步操作都有相应的 Complete 事件。

例如，填充大型 [Recordset](recordset-object-ado.md) 对象可能需要很长时间。 如果您的应用程序编写正确，您可以开始操作，并继续进行其他处理。 最后，当 **ExecuteComplete** 事件填充 **Recordset** 时，您将得到通知。

## <a name="single-event-handlers-and-multiple-objects"></a>单个事件处理程序和多个对象

Microsoft Visual C++ 等编程语言具有的灵活性使您能够用一个事件处理程序来处理多个对象的事件。例如，您可以用一个 **Disconnect** 事件处理程序处理几个 **Connection** 对象的事件。如果其中一个连接结束，则会调用该 **Disconnect** 事件处理程序。您可以确定哪个连接导致该事件，因为事件处理程序对象参数会设置为相应的 **Connection** 对象。


> [!NOTE]
> <P>[!注释] 在 Visual Basic 中无法使用此技术，因为该语言只能将一个对象与一个事件处理程序相关。</P>


