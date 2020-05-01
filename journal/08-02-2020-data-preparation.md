# Data preparation

Automatic recognition of gymnastic human activity requires reference or training data to train our machine to recognize some acrobatic movements, such as backflips or back handsprings. Since these types of movements are performed for a duration of time, just still images of activities are not sufficient. We need the activities recorded in some kind of motion picture format. The device used to capture activities is a GoPro Hero7 Black, with the following basic settings:

* RES - 1080
* FPS - 60
* FOV - Linear
* Low Light - Auto
* Stabilization - Auto
* Protune - Off

## Dataset description

A reference size for the dataset size is taken from this paper (1). The dataset consists of 3 activities (backflip, back handspring and round-off), which are performed for 5 repetitions by 12 subjects (7 male, 5 female).

Each activity is recorded as one still view from eye level angle fully showing the subjects body from head to toe.

[Placeholder: A sample frame from the dataset]

For each activity there needs to be specific start and stop markers, so it could be easily recognized when the activity starts and when does it stop.

The following is a detailed description of each activity and its parameters.

## Backflip

For the backflip, the marking of start and stop points is easy. We mark the start of a backflip as the frame when both heels of the feet of the subject leave the ground and we mark the stop of a backflip as the frame when both heels of the feet touch the ground again. We choose the heels of feet so we can include the full length of the takeoff phase of the backflip in the recording. We choose heels of the feet for the stop mark marker for a similar reason as we don't want to lose the amortization phase of the backflip.

## References

(1) https://easychair.org/publications/preprint/gmWL