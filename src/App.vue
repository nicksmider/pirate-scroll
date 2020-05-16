<template>
  <v-app>
    <v-app-bar
      app
      color="white"
      dark
      class="header-gradient"
    >
      <div class="h-full w-full flex flex-row items-center">
        <p class="text-xl text-white mb-0 header-font">
          the pirate scroll
        </p>
      </div>
    </v-app-bar>

    <v-content class="px-4 bg-gray-100 mb-5">
      <div class="flex flex-row my-wrap">
        <!--Articles-->
        <div class="flex-grow overflow-x-auto overflow-y-hidden pirates-scroll">
          <!--Row-->
          <div>
            <!--Title-->
            <h1 class="mt-5 text-xl mb-0 header-font">
              recent
            </h1>

            <!--Content Holder-->
            <div class="flex flex-row flex-no-wrap overflow-x-auto overflow-y-hidden pirates-scroll mr-5">
              <!--Content-->
              <HeadlineCard
                v-for="card in cards.recent"
                :key="card"
                class="mr-4 my-2"
                :title="card.title"
                :subtitle="card.subtitle"
                :text="card.text"
                :src="card.src"
              />
            </div>
          </div>
          <!--Row-->
          <div>
            <!--Title-->
            <h1 class="mt-5 text-xl mb-0 header-font">
              read again
            </h1>

            <!--Content Holder-->
            <div class="flex flex-row flex-no-wrap overflow-x-auto overflow-y-hidden pirates-scrol mr-5">
              <!--Content-->
              <HeadlineCard
                v-for="card in reverse"
                :key="card"
                class="mr-4 my-2"
                :title="card.title"
                :subtitle="card.subtitle"
                :text="card.text"
                :src="card.src"
              />
            </div>
          </div>
        </div>

        <!--Scores-->
        <div class="my-overflow pirates-scroll">
          <!--Title-->
          <h1 class="mt-5 text-xl mb-0 header-font">
            last 10
          </h1>
          <!--Content Holder-->
          <div class="my-flex my-overflow">
            <!--Content-->
            <ScoreCard
              v-for="score in scores"
              :key="score"
              class="mr-4 mt-2 mb-4"
              :home="score.home"
              :away="score.away"
              :home-score="score.homeScore"
              :away-score="score.awayScore"
              :inning="score.inning"
              :outs="score.outs"
            />
          </div>
        </div>
      </div>
    </v-content>
  </v-app>
</template>

<script>
import HeadlineCard from './components/HeadlineCard';
import ScoreCard from './components/ScoreCard';

export default {
  name: 'App',

  components: {
    HeadlineCard,
    ScoreCard,
  },
  data: () => ({
    cards: {
      recent: [
        {
          title: 'Bell Extended',
          subtitle: 'Dynasty?',
          text: 'Josh Bell signs a 10 year, $800 million extension, the biggest in MLB history.',
          src: 'https://cdnph.upi.com/svc/sv/upi/7771562060938/2019/1/b0ff0523af837e1921fd4eabb1d33106/Pirates-Josh-Bell-blasts-three-homers-vs-Cubs.jpg'
        },
        {
          title: 'Archer Trade Nullified',
          subtitle: 'Falsified Medical Records Revealed',
          text: 'Austin Meadows to report to Brandenton on Monday, Tyler Glasnow recovering from inner lip tattoo infection.',
          src: 'https://cdn.theathletic.com/app/uploads/2020/04/12004921/USATSI_13255981-1024x683.jpg'
        },
        {
          title: '29 Teams Cheated',
          subtitle: 'Pirates Retroactivly Crowned World Series Champs',
          text: 'Neal Huntington is now the most decorated GM in baseball.',
          src: 'https://miro.medium.com/max/2600/1*RZTsoCeXc463-lJo4KmnjQ.jpeg'
        },
        {
          title: 'Nutting Sells',
          subtitle: 'Your Neighbor was Right',
          text: 'Bob Nutting sells the Pittsburgh Pirates for $10 billion, cites online cyberbullying as reason.',
          src: 'https://fobdsports.files.wordpress.com/2019/06/bob-nutting.jpg?w=640'
        },
        {
          title: 'Best Catcher in Baseball?',
          subtitle: 'Move over JT Realmuto',
          text: 'Jacob Stallings leads NL catchers in every statisical category.',
          src: 'https://www.gannett-cdn.com/-mm-/358b6e3f4eb3b9547386edab31a1c1ea0dbb8815/c=222-338-1996-1340/local/-/media/2016/09/24/USATODAY/USATODAY/636102774611025056-USP-MLB-WASHINGTON-NATIONALS-AT-PITTSBURGH-PIRATE-85451272.JPG?width=1774&height=1002&fit=crop&format=pjpg&auto=webp'
        }
      ],
    },
    scores: [
      {
        home: 'PIT',
        away: 'NYY',
        homeScore: 10,
        awayScore: 1,
        inning: 'Top 8th',
        outs: '2 outs',
      },
      {
        home: 'PIT',
        away: 'NYY',
        homeScore: 3,
        awayScore: 0,
        inning: 'Final',
        outs: '',
      },
      {
        home: 'PIT',
        away: 'NYY',
        homeScore: 5,
        awayScore: 4,
        inning: 'Final',
        outs: '',
      },
      {
        home: 'CIN',
        away: 'PIT',
        homeScore: 3,
        awayScore: 7,
        inning: 'Final',
        outs: '',
      },
      {
        home: 'CIN',
        away: 'PIT',
        homeScore: 10,
        awayScore: 28,
        inning: 'Final',
        outs: '',
      },
      {
        home: 'STL',
        away: 'PIT',
        homeScore: 0,
        awayScore: 1,
        inning: 'Final',
        outs: '',
      },
      {
        home: 'STL',
        away: 'PIT',
        homeScore: 2,
        awayScore: 4,
        inning: 'Final',
        outs: '',
      },
      {
        home: 'STL',
        away: 'PIT',
        homeScore: 2,
        awayScore: 5,
        inning: 'Final',
        outs: '',
      },
      {
        home: 'PIT',
        away: 'LAA',
        homeScore: 9,
        awayScore: 12,
        inning: 'Final',
        outs: '',
      },
      {
        home: 'PIT',
        away: 'LAA',
        homeScore: 0,
        awayScore: 3,
        inning: 'Final',
        outs: '',
      }
    ]
  }),
  computed: {
    reverse () {
      return [...this.cards.recent].reverse();
    },
  }
};
</script>

<style scoped>
.header-font {
  font-family: PirateFont, Fallback, sans-serif;
}

h1 {
  @apply text-pirate-black;
}

.header-gradient {
  background: linear-gradient(
    0deg,
    var(--pirate-gold) 15%,
    var(--pirate-black) 15%,
    var(--pirate-black) 85%,
    var(--pirate-gold) 85%
  );
}

.my-wrap {
  flex-wrap: nowrap;
}

@media (max-width: 600px) {
  .my-wrap {
    flex-wrap: wrap;
  }
  .my-flex {
    display: flex;
    flex-direction: row;
  }
  .my-overflow {
    overflow-x: auto;
  }
}

.scroll-gradient {
  background: linear-gradient(
    45deg,
    var(--pirate-black),
    var(--pirate-gold),
    var(--pirate-black)
  );
}

::-webkit-scrollbar {
  height: 5px;
}

::-webkit-scrollbar-track {
  @apply scroll-gradient;
}

::-webkit-scrollbar-thumb {
  background: transparent;
  box-shadow: 0px 0px 0px 100000vh rgb(247, 250, 252);
  border-radius: 2px !important;
}
</style>