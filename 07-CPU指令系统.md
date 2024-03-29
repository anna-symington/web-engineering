# CPU 指令系统

  CPU可以根据使用的指令集分成两大类：复杂指令集（CISC）和精简指令集（RISC）。

## 复杂指令集（CISC）

  复杂指令集（CISC）的特点是其包含的指令条目数很多，至少在300条以上，甚至会超过500条。这是因为在很长时间以来，计算机的性能提高往往都是通过增加硬件的复杂性来获得的。随着集成电路技术的迅速发展，为了提高程序的运行速度，硬件工程师们采用的方法就是不断的增加可实现复杂功能的指令，以及增加多种灵活的编制方式。然而，这种做法会让硬件变得越来越复杂，造价也会变得越来越高。

  在支持复杂指令的CPU中，程序的各条指令都是按顺序来串行执行的，同时每条指令当中的各个操作也都是按顺序来串行执行的。这种指令执行的方法被称为顺序执行法。然而，顺序执行法会导致计算机内部的各个部件的利用率非常低，从而导致执行速度很缓慢，效率也很低下。

  举个例子，假设在一个生产车间中，我们现在想加工十个零件，然后我们雇了三个工人。如果这三个工人按照顺序执行法工作，那么在任何时候，只有一个人在工作，其他两个人都在闲着。这就导致整体的利用率非常低下，执行速度很缓慢，效率也很低下。

  因此，我们可以得出结论，复杂指令集和顺序执行法虽然可以实现复杂的功能，但是由于其效率低下，所以并不是一种理想的解决方案。在实际的计算机系统设计中，我们需要寻找更有效的方法来提高计算机的性能。

## 精简指令集（RISC）

  人们发现在典型的程序中，有80%的语句使用的都是计算机中的20%的指令，而这20%的指令又都属于简单指令。
  
  人们开始质疑复杂指令的必要性。如果80%的语句都使用简单指令，那么为什么还要花费大量的时间和精力去研究复杂指令呢？尤其是当这些复杂指令会严重影响CPU的执行速度时，人们开始考虑是否可以完全放弃使用复杂指令
  
  然而，问题在于剩下的20%的语句。如果不使用复杂指令，那么这些语句该如何处理呢？显然，忽视这些语句并不是一个可行的解决方案。于是，人们提出了一个妙招：使用简单语句的重新组合来模拟复杂指令。

  这样，精简指令集就逐步的诞生了。

## 比较

精简指令集：
  - **精简指令集的第一个优势在于它能够提高计算机的运行速度。** 精简指令集的设计理念是使用更少的指令，每个指令执行的任务更单一，从而提高了指令的执行效率。
  - **它的设计更为简洁，这使得精简指令集更易于设计，可以降低成本并提高可靠性。** 相比之下，复杂指令集由于其复杂性，设计难度更大，成本也更高。
  - **精简指令集的第三个优势在于它能够有效地支持一些高级语言，如Python、Go和Java等。** 这是因为精简指令集的设计理念是让硬件做更少的工作，而将更多的工作交给软件，也就是编程语言和编译器。

复杂指令集：
 - **复杂指令集的优势在于其指令系统非常丰富，有专用的指令来完成特定的功能，因此在处理一些特殊的任务时效率很高。**

执行方法差别：
 - 复杂指令集执行指令的方法是顺序执行，这导致计算机各部分的利用率很低，执行速度慢，效率低。
 - 精简指令集不再使用顺序执行法，而是采用了一种叫做流水线技术的方法。流水线技术能够保证大部分的指令在一个时钟周期内就能完成，因此，通过流水线技术，我们可以大大提升工作效率。

![image](https://github.com/anna-symington/web-engineering/assets/160561460/5d869d6e-d836-46e7-a485-97b1d88ec585)

## 顺序执行法

  假设在一个生产车间中，我们要加工十个零件，现在我们雇了三个工人。如果这三个工人按照顺序执行法去工作，那么他们的工作方式就是这样的：

  首先，第一个工人开始加工第一个零件，此时他处于工作状态，而其他两个工人则闲着没有活干。当第一个工人加工完第一个零件后，他把零件传给了第二个工人。此时，第二个工人开始加工这个零件，处于工作状态，而一号工人和三号工人处于闲置状态。当二号工人加工完零件后，他把零件传给了三号工人。此时，三号工人开始加工零件，处于工作状态，而一号和二号工人则闲着没有活干。直到三号工人也加工完成了零件，这个零件才可以正常地被售卖，走向市场。然后，这个过程以此类推，周而复始。

  在这样的顺序执行法中，我们会发现，生产车间在同一时间内，永远只有一个工人在工作。这就意味着，你忙的时候我闲着，我忙的时候你闲着，总之，大家从来没有一起忙过。这就导致我们的生产车间的执行速度非常缓慢，利用率非常低下，从而使得工作效率非常低。

## 流水线技术

  精简指令集不使用顺序执行法，而是采用了另外一种方法，那就是流水线技术。我们在上节课中说过，流水线技术能够保证大部分的指令在一个时钟周期内被完成。

  那么，什么是流水线技术呢？流水线技术其实非常简单。流水线就是一种将指令分解成多个小的步骤，然后让几条不同的指令的各个步骤进行重叠，从而实现让几条指令一起去处理的效果，目的就是为了加快程序的运行速度。

  我们还是用刚才的例子来解释一下。还是那个生产车间，还是要加工十个零件，我们还是雇了三个工人。这次，我们说三个工人不再使用顺序执行法，而是采用我们现在讲的流水线方式。我们看看这次三个工人怎么干活。

  首先，跟刚才一样，一号工人先去加工一个零件。因为他现在加工的是第一个零件，前面没有零件加工，所以在一号工人加工第一个零件的时候，二号工人和三号工人确实没有活干，这是没有办法的。但是，等到一号工人加工完这个零件之后，他把零件传给了二号工人，此时二号工人就开始加工第一个零件。为了提高整个的工作效率，此时的一号工人并没有闲着，而是继续去加工第二个零件。那么此时，我们会发现，在生产车间中，就有两个工人一起在干活了。
  
  等到二号工人把第一个零件加工完成后，他把零件传给了三号工人，于是三号工人开始加工第一个零件。而与此同时，一号工人刚才加工的第二个零件已经搞定了，于是他把第二个零件传给了二号工人。那就意味着，此时的二号工人也在加工第二个零件。而又与此同时，一号工人又可以去加工第三个零件。也就是说，到了第三个时刻，我们能够非常清楚地看到，现在三个工人都没闲着，都在干活了。

  你看，通过这样的方法，我们不就能够大大地提升我们的工作效率了吗？我们的工作产出比不就大大提升了吗？那么，这就是所谓的流水线技术。
  
![image](https://github.com/anna-symington/web-engineering/assets/160561460/f47150cd-7a3c-48db-8714-84a35290edcd)

我们已经明白了流水线技术的基础工作原理。通过这个原理，我们可以得到一个公式，用来计算用流水线技术执行N条命令所需的时间。这个公式是

**(T1 + T2 + T3)+(n - 1) * T**

在这个公式中，**T1**、**T2**和**T3**分别代表取指令、译码和执行这三个步骤所需的时间，**n**代表要执行的指令的总数，**T**代表每一个部件完成所需的时间。

让我们用一个例子来说明这个公式的应用。假设我们的取指令、译码和执行这三个步骤所需的时间都是一纳秒，现在我们想要让CPU执行完100条指令。那么，根据上述公式，我们可以计算出，用流水线技术执行100条指令所需的总时间是：

**1 + 1 + 1 + (100-1) * 1 = 102 纳秒**。

这就是说，采用流水线技术，执行了100条指令，所花费的总时间是102纳秒。

然而，如果我们不使用流水线技术，而是使用早期的顺序执行方法，那么，每条指令从开始执行到完毕，都需要经过取指令、译码和执行这三个步骤，每个步骤都需要一纳秒，所以每完成一个指令需要花费三纳秒时间。因此，完成100条指令的执行，需要花费

**3 * 100 = 300 纳秒**。

由此可见，采用流水线技术，我们的时间能够大大地节省，从而提升了效率，使得CPU的运行速度可以大大提高。这就是流水线技术能够很好地提高工作效率的原因。

然而，在实际的工作过程中，我们需要注意的是，不同的部件所需的时间可能并不完全一样。比如，取指令部件可能需要两纳秒，译码部件也可能需要两纳秒，而执行部件可能只需要一纳秒。这时候，我们应该如何去计算完成100条指令所需的时间呢？

这时，我们需要引入一个新的概念，那就是流水线的瓶颈。在线性流水线中，执行时间最长的那一段就成了整个流水线的瓶颈。因此，执行的总时间主要取决于流水操作步骤中最长时间的那个操作。也就是说，我们在计算总时间时，应该取最长的那个时间，也就是两纳秒。

所以，如果取指令部件和译码部件都需要两纳秒，而执行部件只需要一纳秒，那么，完成100条指令所需的时间应该是：

**2 + 2 + 1 + (100-1) * 2 = 203 纳秒**。

这就是说，当不同的部件所需的时间不一样时，我们应该考虑流水线的瓶颈，以确保我们的计算结果是准确的。这也是我们在使用流水线技术时需要注意的一个重要问题。只有这样，我们才能真正地提高我们的工作效率，使得CPU的运行速度可以大大提高。

![image](https://github.com/anna-symington/web-engineering/assets/160561460/18e22cb3-6139-446e-b1bf-4328f8df23aa)

### 流水线性能

流水线的性能主要受三个参数的影响，这三个参数是吞吐率、加速比和效率。下面我们将详细解释这三个参数。

#### 吞吐率
吞吐率是指流水线在单位时间内可以处理的任务或执行指令的个数。计算吞吐率的公式是

![image](https://github.com/anna-symington/web-engineering/assets/160561460/24f81518-b0ed-4fd9-bbdd-47ccb9f7768e)


，其中， **N** 是需要执行的指令的总条目数，**T** 是按照流水线技术完成这些指令所花费的总时间。

例如，如果我们需要执行100条指令，按照流水线技术，我们花费的总时间是203纳秒，那么吞吐率就是

![image](https://github.com/anna-symington/web-engineering/assets/160561460/704d281b-aa58-4004-9460-d4f97a620053)

。但是，因为这个203是纳秒，而我们的吞吐率单位是秒，所以在计算的时候，我们需要将纳秒转换为秒，即乘以一个十的九次方。

#### 加速比
加速比是指采用串行顺序方式和采用流水线方式的比值。如果用顺序执行方法花费500纳秒，用流水线技术花费203纳秒，那么加速比就是

![image](https://github.com/anna-symington/web-engineering/assets/160561460/edb6fcb1-802c-4ca5-b71f-76eda1b0cf91)

。加速比的数值越大，说明这条流水线的工作安排方式就越好。

#### 效率
效率是指流水线中各个部件的利用率。在流水线开始工作的时候，存在一个建立时间，在结束的时候，存在一个排空时间，因此流水线中总是有某一个部件在某一些时间是处于闲置状态的。效率就是处于工作状态的部件和总部件的比值。例如，如果同时处于工作状态的部件有100个，总部件有102个，那么效率就是

![image](https://github.com/anna-symington/web-engineering/assets/160561460/5f87fc17-2d6d-4585-9368-e8a8d7889072)

。
总的来说，吞吐率、加速比和效率这三个参数是影响流水线性能的主要因素。
