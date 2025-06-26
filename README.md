# JAVACODE2
package Pack1;

class PlanetThread extends Thread {
    private String planetName;
    private double gravityRatio;
    private double earthWeight;

    public PlanetThread(String planetName, double gravityRatio, double earthWeight) {
        this.planetName = planetName;
        this.gravityRatio = gravityRatio;
        this.earthWeight = earthWeight;
    }

    @Override
    public void run() {
        double weightOnPlanet = earthWeight * gravityRatio;
        System.out.println("Weight on " + planetName + ": " + weightOnPlanet + " kg");
    }
}

public class PlanetWeightCalculator {

    public static void main(String[] args) {
        double earthWeight = 70.0;

        Thread mercury = new PlanetThread("Mercury", 0.38, earthWeight);
        Thread venus = new PlanetThread("Venus", 0.91, earthWeight);
        Thread mars = new PlanetThread("Mars", 0.38, earthWeight);
        Thread jupiter = new PlanetThread("Jupiter", 2.34, earthWeight);
        Thread saturn = new PlanetThread("Saturn", 1.06, earthWeight);
        Thread uranus = new PlanetThread("Uranus", 0.92, earthWeight);
        Thread neptune = new PlanetThread("Neptune", 1.19, earthWeight);

        mercury.start();
        venus.start();
        mars.start();
        jupiter.start();
        saturn.start();
        uranus.start();
        neptune.start();
    }
}
