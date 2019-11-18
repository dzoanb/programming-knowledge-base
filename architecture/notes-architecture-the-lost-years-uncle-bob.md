---
description: 'Notes and thoughts on https://youtu.be/HhNIttd87xs'
---

# \[Notes\] Architecture: The Lost Years - Uncle Bob

* Architecture is there to keep the arrows in your diagrams right.
* Make the arrows point to your application, that means it's independent from things like the environment, the GUI, database, third-party frameworks.
* Set Boundary protocols between your code, your domain and the elements interacting with the user. In the end, it shouldn't matter how you get the inputs and who consumes your output.
* Boundaries serve for communication in both directions:
  *  The input boundary that's called by the "outside" of your application, it's the protocol your Interactor would implement to receive a RequestModel with all the data.
  *  The output boundary is called by the Interactor when the application is done processing, it's the protocol the "outside" would implement to receive ResponseModel containing results.
* Both RequestModel and ResponseModel types should be just a plain ol' data structures with no logic.
* The application agnostic logic lives in Entities.
* The application aware logic belongs in the Interactor.
* In fact, all the arrows should point from the Interactor outwards:
  * Bondaries are either called or implemented by it;
  * Entities are used by the Interactor to perform calculations, never the other way around.



