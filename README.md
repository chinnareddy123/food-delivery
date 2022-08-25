# food-order
#html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <meta
      name="description"
      content="Web site created using create-react-app"
    />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
        <title>React App</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
  </body>
</html>

#.json
{
 "short_name": "React App",
  "name": "Create React App Sample",
  "icons": [
    {
      "src": "favicon.ico",
      "sizes": "64x64 32x32 24x24 16x16",
      "type": "image/x-icon"
    },
    {
      "src": "logo192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
    {
      "src": "logo512.png",
      "type": "image/png",
      "sizes": "512x512"
    }
  ],
  "start_url": ".",
  "display": "standalone",
  "theme_color": "#000000",
  "background_color": "#ffffff"
}

#javascript
manifesto.js
import Navbar from '../Navbar/Navbar';
import {Button} from '../../Globalstyles';
import {
    HeroContainer,
    HeroContent,
    HeroContentText,
    HeroTitle,
    HeroTitleText,
    HeroSubTitle,
    HeroText,
    HeroBtn,

} from './Hero.styles';

const Hero = () =>{
    return(
        <div>
           <HeroContainer>
               <Navbar/>
               <HeroContent>
                   <HeroContentText>
                        <HeroTitle>
                            <HeroTitleText>Healthy</HeroTitleText>
                            <HeroTitleText>Meals All Day</HeroTitleText>
                        </HeroTitle>
                        <HeroSubTitle>For a longer Life</HeroSubTitle>
                        <HeroText>
                            Get a fresh and tasty recepies that are well balanced and 
                            will improve your wellness, plus add nutrients to your body.
                        </HeroText>
                        <HeroBtn to="/order-now">
                           <Button primary big bigFont bigRadius>Pick your meals</Button>
                        </HeroBtn>
                   </HeroContentText>
               </HeroContent>
           </HeroContainer>
        </div>
    )
}

#styles.js
import styled from 'styled-components';
import {Link} from 'react-router-dom';
import ImgBg from '../../images/hero-bg.png';

export const HeroContainer = styled.div`
background-image: linear-gradient( to top right, rgba(11, 10, 10, 0.38), rgba(11, 10, 10, 0.19)), url(${ImgBg});
background-position: center;
background-repeat: no-repeat;
background-size: cover;
height: 74vh;
@media only screen and (max-width:1600px) {
    height: 85vh;
}
`;

export const HeroContent = styled.section`
height: 100%;
width: 100%;
position: relative;
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
text-align: center;
color: #FFFEFE;
@media only screen and (max-width:375px) {
    text-align: start;
    height: 80%;
}
`;

export const HeroContentText = styled.div`
width: 50%;
padding-top: 5rem;
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
@media only screen and (max-width:600px) {
    width: 80%;
}
@media only screen and (max-width:375px) {
    position: absolute;
    align-items: flex-start;
}
`;

export const HeroTitle = styled.h1`
font-size: clamp(1rem, 10vw, 5rem);
font-weight: 900;
letter-spacing: .5rem;
line-height: 1.3;
`;

export const HeroTitleText = styled.span`
display: block;
`;

export const HeroSubTitle = styled.h2`
font-size: clamp(2rem, 3vw, 4rem);
font-weight: 300;
letter-spacing: 1rem;
padding-top: 1rem;
`;

export const HeroText = styled.h3`
font-size: clamp(2rem, 2.5vw, 3rem);
font-weight: 400;
padding: 2.5rem 2rem;
@media only screen and (max-width:375px) {
    padding: 1.5rem 0;
}
`;

export const HeroBtn = styled(Link)`
text-decoration: none;
outline: none;
border: none;
`;

#recipes.js
import {OutlineButton} from '../../Globalstyles';
import SalmonImg from '../../images/salmon.png';
import ChickenImg from '../../images/Chicken.svg';
import PizzaImg from '../../images/Italian-pizza.svg';
import PastaImg from '../../images/Pasta.svg';
import SaladImg from '../../images/salad.png';
import {
    RecipeContainer,
    RecipeWrapper,
    RecipeTitle,
    RecipeContentContainer,
    RecipeTabContainer,
    RecipeBtn,
    RecipeCardWrapper,
    RecipeFeature,
    RecipeFeatureContent,
    RecipeFeatureTitle,
    RecipeFeatureText,
    RecipeFeatureDetails,
    RecipeFeatureItem,
    RecipeItemTitle,
    RecipeItemContent,
    RecipeItemIcon,
    RecipeItemText,
    RecipeCardSection,
    RecipeSmallCards,
    RecipeCard,
    RecipeCardContent,
    RecipeCardHeading,
    RecipeCardDetails,
    RecipeCardItems,
    RecipeCardTitle,
    RecipeCardItem,
    RecipeCardIcon,
    RecipeCardText,
    RecipeImg,
    Img,



} from './Recipes.styles';
const Recipes = () => {
    return (
        <div>
            <RecipeWrapper>
                <RecipeContainer>
                    <RecipeTitle>Recipes</RecipeTitle>
                    <RecipeContentContainer>
                        <RecipeTabContainer>
                            <RecipeBtn to='/sea-food'>
                                <OutlineButton big bigFont bigRadius>Sea Food</OutlineButton>
                            </RecipeBtn>
                            <RecipeBtn to='/Vegetarian'>
                                <OutlineButton big bigFont bigRadius>Vegetarian</OutlineButton>  
                            </RecipeBtn>
                            <RecipeBtn to='/meat'>
                                <OutlineButton big bigFont bigRadius>Meat and Poultry</OutlineButton>
                            </RecipeBtn>
                            <RecipeBtn to='/easy-preps'>
                                <OutlineButton big bigFont bigRadius>Easy meal preps</OutlineButton>  
                            </RecipeBtn>
                        </RecipeTabContainer>
                        <RecipeCardWrapper>
                            <RecipeFeature>
                                <RecipeImg src={SalmonImg} alt="Salmon Recipe"/>
                                <RecipeFeatureContent>
                                    <RecipeFeatureTitle>
                                        Salmon and Hot Honey Butter
                                    </RecipeFeatureTitle>
                                    <RecipeFeatureText>
                                        The hot honey kinda sounds like a hype name used before the 20s, (I used it back then). 
                                        It’s a pefect coating for the salmon to enrinch it with sweetness and heat. 
                                    </RecipeFeatureText>
                                    <RecipeFeatureDetails>
                                        <RecipeFeatureItem>
                                            <RecipeItemTitle>Serving</RecipeItemTitle>
                                            <RecipeItemContent>
                                                <RecipeItemIcon/>
                                                <RecipeItemText>2</RecipeItemText>
                                            </RecipeItemContent>

                                        </RecipeFeatureItem>
                                        <RecipeFeatureItem>
                                            <RecipeItemTitle>Cook time</RecipeItemTitle>
                                            <RecipeItemText>35-45 min</RecipeItemText>
                                        </RecipeFeatureItem>
                                        <RecipeFeatureItem>
                                            <RecipeItemTitle>Difficulty level</RecipeItemTitle>
                                            <RecipeItemText>20%</RecipeItemText>
                                        </RecipeFeatureItem>

                                    </RecipeFeatureDetails> 
                                </RecipeFeatureContent>
                            </RecipeFeature>
                            <RecipeCardSection>
                                <RecipeSmallCards>
                                    <RecipeCard>
                                        <Img src={ChickenImg} alt="Chicken Recipe"/>
                                        <RecipeCardContent>
                                            <RecipeCardHeading>
                                                Pretzel-Crusted Chicken
                                            </RecipeCardHeading>
                                            <RecipeCardDetails>
                                                <RecipeCardItems>
                                                        <RecipeCardTitle>Serving</RecipeCardTitle>
                                                        <RecipeCardItem>
                                                            <RecipeCardIcon/>
                                                            <RecipeCardText>2</RecipeCardText>
                                                        </RecipeCardItem>

                                                    </RecipeCardItems>
                                                <RecipeCardItems>
                                                    <RecipeCardTitle>Cook time</RecipeCardTitle>
                                                    <RecipeCardText>30-45 min</RecipeCardText>
                                                </RecipeCardItems>
                                                <RecipeCardItems>
                                                    <RecipeCardTitle>Difficulty level</RecipeCardTitle>
                                                    <RecipeCardText>20%</RecipeCardText>
                                                </RecipeCardItems>

                                            </RecipeCardDetails>
                                        </RecipeCardContent>

                                    </RecipeCard>
                                    <RecipeCard>
                                        <Img src={SaladImg} alt="Salad Recipe"/>
                                        <RecipeCardContent>
                                            <RecipeCardHeading>
                                                 Sesame Asian Salad
                                            </RecipeCardHeading>
                                            <RecipeCardDetails>
                                                <RecipeCardItems>
                                                        <RecipeCardTitle>Serving</RecipeCardTitle>
                                                        <RecipeCardItem>
                                                            <RecipeCardIcon/>
                                                            <RecipeCardText>2</RecipeCardText>
                                                        </RecipeCardItem>

                                                    </RecipeCardItems>
                                                <RecipeCardItems>
                                                    <RecipeCardTitle>Cook time</RecipeCardTitle>
                                                    <RecipeCardText>10-15 min</RecipeCardText>
                                                </RecipeCardItems>
                                                <RecipeCardItems>
                                                    <RecipeCardTitle>Difficulty level</RecipeCardTitle>
                                                    <RecipeCardText>10%</RecipeCardText>
                                                </RecipeCardItems>

                                            </RecipeCardDetails>
                                        </RecipeCardContent>

                                    </RecipeCard>
                                </RecipeSmallCards>
                                <RecipeSmallCards>
                                    <RecipeCard>
                                        <Img src={PizzaImg} alt="Pizza Recipe"/>
                                        <RecipeCardContent>
                                            <RecipeCardHeading>
                                                Italian Pizza with Cheese
                                            </RecipeCardHeading>
                                            <RecipeCardDetails>
                                                <RecipeCardItems>
                                                        <RecipeCardTitle>Serving</RecipeCardTitle>
                                                        <RecipeCardItem>
                                                            <RecipeCardIcon/>
                                                            <RecipeCardText>2</RecipeCardText>
                                                        </RecipeCardItem>

                                                    </RecipeCardItems>
                                                <RecipeCardItems>
                                                    <RecipeCardTitle>Cook time</RecipeCardTitle>
                                                    <RecipeCardText>30-45 min</RecipeCardText>
                                                </RecipeCardItems>
                                                <RecipeCardItems>
                                                    <RecipeCardTitle>Difficulty level</RecipeCardTitle>
                                                    <RecipeCardText>20%</RecipeCardText>
                                                </RecipeCardItems>

                                            </RecipeCardDetails>
                                        </RecipeCardContent>

                                    </RecipeCard>
                                    <RecipeCard>
                                        <Img src={PastaImg} alt="Pasta Recipe"/>
                                        <RecipeCardContent>
                                            <RecipeCardHeading>
                                               Pasta with creamy sause
                                            </RecipeCardHeading>
                                            <RecipeCardDetails>
                                                <RecipeCardItems>
                                                        <RecipeCardTitle>Serving</RecipeCardTitle>
                                                        <RecipeCardItem>
                                                            <RecipeCardIcon/>
                                                            <RecipeCardText>2</RecipeCardText>
                                                        </RecipeCardItem>

                                                    </RecipeCardItems>
                                                <RecipeCardItems>
                                                    <RecipeCardTitle>Cook time</RecipeCardTitle>
                                                    <RecipeCardText>10-15 min</RecipeCardText>
                                                </RecipeCardItems>
                                                <RecipeCardItems>
                                                    <RecipeCardTitle>Difficulty level</RecipeCardTitle>
                                                    <RecipeCardText>10%</RecipeCardText>
                                                </RecipeCardItems>

                                            </RecipeCardDetails>
                                        </RecipeCardContent>

                                    </RecipeCard>
                                </RecipeSmallCards>

                            </RecipeCardSection>
                            
                        </RecipeCardWrapper>
                    </RecipeContentContainer>
                </RecipeContainer>
            </RecipeWrapper>
            
        </div>
    );
}

#recipes.styles.js
import styled from 'styled-components';
import {HiUsers} from 'react-icons/hi';
import {Link} from 'react-router-dom';
import {Container} from '../../Globalstyles';

export const RecipeWrapper = styled.section`
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
margin: 6rem 0;
`;

export const RecipeContainer = styled(Container)`
display: flex;
flex-direction: column;
${Container};
`;

export const RecipeTitle = styled.h2`
font-size: clamp(2rem, 8vw, 5rem);
text-align: center;
margin-bottom: 3rem;
font-weight: bold;
@media only screen and (max-width:700px){
    margin-bottom: 0;
}
`;

export const RecipeContentContainer = styled.div`
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
`;

export const RecipeTabContainer = styled.div`
display: flex;
justify-content:center;
align-items:center;                                                                                                     
@media only screen and (max-width:700px){
    display: none;
}                                                                            
`;

export const RecipeBtn = styled(Link)`
&:not(:last-child){
    margin-right: 3rem;
}
@media only screen and (max-width: 700px){
    display: none;
 }
`;

//Recipe card section

export const RecipeCardWrapper = styled.div`                                                
display: flex;                                                                                                                                                                                                                                                                                                                                                                                                                                        
justify-content: space-between;
align-items: center;
margin-top: 6rem;
flex-direction: column;
@media only screen and (min-width:1800px) {
    flex-direction: row;
}
`;

export const RecipeFeature = styled.div`
display: flex;
justify-content: center;
align-items: center;
width: 650px;
height: 320px;
background-color: #fff;
box-shadow: 0px 8px 30px rgba(0, 0, 0, 0.18);
border-radius: 40px;
transition: all .4s ease;
margin-bottom: 5rem;
cursor: pointer;
@media only screen and (min-width: 1800px){
    margin-right: 10rem;
    padding: 0;
}
&:hover{
    box-shadow: 0px 10px 80px rgba(0, 0, 0, 0.12);
    transform: scale(1.05);
    background-color: #333;
    color: #fff;
}
@media only screen and (min-width:1000px) {
    flex-direction: row;
}
@media only screen and (max-width:900px){
    margin-bottom: 10rem;
}
@media only screen and (max-width:700px){
    width: 550px;
    margin-bottom: 3rem;
    &:hover{
        transform: scale(1.02);
    }
}
@media only screen and (max-width:600px){
    width: 500px;
}
@media only screen and (max-width:500px){
    width: 380px;
    height: 300px;
    flex-direction: column;
    justify-content: flex-start;
    box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.10);
}
@media only screen and (max-width:400px){
    width: 330px;
}
`;

export const RecipeImg = styled.img`
height: 80%;
margin-top: 2rem;
margin-left: 2rem;
transition: all .5s ease;
&:hover {
    transform: scale(1.14) rotate(360deg);
}
@media only screen and (max-width:700px){
    height: 58%;
}
@media only screen and (max-width:600px){
    height: 50%;
}
@media only screen and (max-width:500px){
    height: 30%;
}
`;

export const RecipeFeatureContent = styled.div`
display: flex;
flex-direction: column;
justify-content: center;
padding: 2rem;
@media only screen and (max-width:500px){
    padding: 2rem;
    align-items: center;
}
`;

export const RecipeFeatureTitle = styled.h3`
font-size: 3.6rem;
font-weight: 400;
line-height: 1.3;
margin-bottom: .6rem;
@media only screen and (max-width:700px){
    font-size: 3rem;
}
@media only screen and (max-width:600px){
    font-size: 2.5rem;
}
@media only screen and (max-width:400px){
    font-size: 2rem;
}
`;

export const RecipeFeatureText = styled.p`
font-size: 1.6rem;
padding-bottom: 1.3rem;
@media only screen and (max-width:700px){
    font-size: 1.4rem;
}
@media only screen and (max-width:400px){
    font-size: 1.3rem;
}
`;

export const RecipeFeatureDetails = styled.div`
display: flex;
align-items: center;
`;

export const RecipeFeatureItem = styled.div`
display: flex;
align-items: flex-start;
flex-direction: column;
margin-right: 2.5rem;
`;

export const RecipeItemTitle = styled.h4`
font-size: 1.4rem;
@media only screen and (max-width:400px){
    font-size: 1.3rem;
}
`;

export const RecipeItemContent = styled.div`
display: flex;
align-items: center;
`;

export const RecipeItemIcon = styled(HiUsers)`
 color: #E38B06;
 font-size: 3rem;
 padding-right: 1rem;
`;

export const RecipeItemText = styled.p`
font-size: 1.8rem;
@media only screen and (max-width:700px){
    font-size: 1.6rem;
}
`;

export const RecipeCardSection = styled.div`
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
@media only screen and (min-width: 900px) {
    flex-direction: row;
}
`;

export const RecipeSmallCards = styled.div`
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
@media only screen and (min-width: 1200px){
    margin-left: 2rem;
}
@media only screen and (min-width: 1500px){
    margin-left: 3.5rem;
}
`;

export const RecipeCard = styled.div`
display: flex;
justify-content: center;
align-items: center;
width: 500px;
height: 130px;
background: #FFFFFF;
box-shadow: 0px 10px 30px rgba(0, 0, 0, 0.15);
border-radius: 20px;
transition: all .5s ease;
margin-bottom: 4rem;
cursor: pointer;
&:hover {
    background-color: #333;
    color: #fff;
    transform: scale(1.05);
    box-shadow: 0px 10px 50px rgba(0, 0, 0, 0.2);
}
@media only screen and (max-width:1200px) {
    width: 397px;
    margin-right: 5rem;
}
@media only screen and (max-width:1000px) {
    width: 420px;
    margin-right: 2.5rem;
}
 
@media only screen and (max-width:700px){
    width: 380px;
    &:hover {
    transform: scale(1.1);
    }
}
@media only screen and (max-width:500px){
    margin-right: 0;
    &:hover {
    transform: scale(1);
    }
}
@media only screen and (max-width:400px){
    flex-direction: column;
    width: 280px;
}
`;

export const RecipeCardImg = styled.div`
height: 10.3rem;
margin-left: -10rem;
`;

export const RecipeCardContent = styled.div`
display: flex;
flex-direction: column;
align-items: flex-start;
padding: 0 2rem;
`;

export const RecipeCardHeading = styled.h3`
font-size: 2.4rem;
font-weight: 400;
@media only screen and (max-width:700px){
    font-size: 2rem;
}
`;

export const RecipeCardDetails = styled.div`
display: flex;
align-items: center;
margin-top: 1.5rem;
`;

export const RecipeCardItems = styled.div`
display: flex;
flex-direction: column;
align-items: flex-start;
text-align: center;
&:not(:last-child){
    margin-right: 2.5rem;
}
`;

export const RecipeCardTitle = styled.h4`
font-size: 1.4rem;
@media only screen and (max-width:700px){
    font-size: 1.2rem;
}
`;

export const RecipeCardItem = styled.div`
display: flex;
justify-content: center;
align-items: center;
margin-right: 2.5rem;
`;

export const RecipeCardIcon = styled(HiUsers)`
 color: #E38B06;
 font-size: 2rem;
 margin-right: 1.3rem;
@media only screen and (max-width:700px){
    font-size: 1.5rem;
    margin-right: 1rem;
 }
`;

export const RecipeCardText = styled.p`
font-size: 1.4rem;
@media only screen and (max-width:700px){
    font-size: 1.2rem;
}
`;



export const RecipeFeatureImg = styled.div`
width: 100%;
display: flex;
justify-content: center;
align-items: center;
height: 100%;
`;

export const Img = styled.img`
height: 10rem;
transition: all .5s ease;
&:hover {
    transform: scale(1.06) rotate(360deg);
}
@media only screen and (max-width: 1000px){
    height: 9rem;
}
@media only screen and (max-width: 400px){
    display: none;
}

#welcome.js
import {
    WelcomeContainer, 
    WelcomeContent,
    WelcomeImg, 
    WelcomeContentText,
    WelcomeContentTitle,
    WelcomeText,
    Img
} from './Welcome.styles';
import PizzaImg from '../../images/pizza.png';
const Welcome = () => {
    return (
        <div>
            <WelcomeContainer>
                <WelcomeContent>
                    <WelcomeImg>
                        <Img src={PizzaImg} alt=" Delious Pizza"/>
                    </WelcomeImg>
                    <WelcomeContentText>
                        <WelcomeContentTitle>Welcome</WelcomeContentTitle>
                        <WelcomeText>
                            Home made is a great way to make meals at home that are health and enjoyable. 
                            We have a variety of categories to choose from that help meet your needs in your health journey.
                            You can customize the ingredients you want to be added in your meal. This can be due to health 
                            resources, you don’t have to use evrything in the list.
                        </WelcomeText>
                        <WelcomeText>
                            The order will be sent straight to your door step in less then 
                            1hr pre-packed for you in portions. 
                            Start cooking by folloing the visual guide in your order and serve your family a health meal.
                        </WelcomeText>
                    </WelcomeContentText>
                </WelcomeContent>
                

            </WelcomeContainer>
            
        </div>
    )
}
#welcome.styles.js
import styled from 'styled-components';
import PizzaBg from '../../images/hero-bg.png';

export const WelcomeContainer = styled.section`
display: flex;
justify-content: center;
align-items: center;
width: 100%;
margin-top: 7rem;
`;

export const WelcomeContent = styled.div`
display: flex;
justify-content: center;
align-items: center;
background: #fff;
@media only screen and (max-width:1000px) {
    flex-direction: column;
}
`;

export const WelcomeImg = styled.div`
height: 100%;
width: 100%;
display: flex;
justify-content: center;
`;

export const Img = styled.img`
background-size: cover;
background-position: center;
background-repeat: no-repeat;
object-fit: cover;
border-radius: 4px;
height: 300px;
@media only screen and (min-width:300px) {
    width: 300px;
}
@media only screen and (min-width:400px) {
    width: 400px;
}
@media only screen and (min-width:600px) {
    width: 500px;
}
@media only screen and (min-width:800px) {
    width: 800px;
}
@media only screen and (min-width:1000px) {
    width: 500px;
    height: 400px;
}
@media only screen and (min-width:1200px) {
    width: 600px;
}
@media only screen and (min-width:1500px) {
    width: 750px;
}
@media only screen and (min-width:1800px) {
    width: 900px;
}
`;

export const WelcomeContentText = styled.div`
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
padding: 3rem;
@media only screen and (min-width:1200px) {
    padding: 3rem 6rem;
}
@media only screen and (min-width:1500px) {
    padding: 3rem 9rem;
}
`;

export const WelcomeContentTitle = styled.h2`
font-size: 3.6rem;
font-weight: bold;
`;

export const WelcomeText = styled.p`
font-size: 1.8rem;
&:not(:last-child) {
    margin-bottom: 2rem;
}

#imdex.js
export {default as Navbar} from './Navbar/Navbar';
export {default as Welcome} from './Welcome/Welcome';
export {default as Recipes} from './Recipes/Recipes';
